# Handling PUSH-notifications
### Configuring the application
To be able to send APNS notifications to Apple servers or GCM notifications to Google servers, application certificates (APNS) or an application key (GCM) must be specified in the application settings.
### Subscribing to notifications
To subscribe to notifications, the client must invoke the account.registerDevice query, passing in token_type and token as parameters that identify the current device. It is useful to repeat this query at least once every 24 hours or when restarting the application. Use account.unregisterDevice to unsubscribe.
The following token_types are supported:
- 1 - APNS (device token for apple push)
- 2 - FCM (firebase token for google firebase)
- 3 - MPNS (channel URI for microsoft push)
- 4 - Simple push (endpoint for firefox's deprecated simple push API): note that this push type can also be used by an open source push notification spec like UnifiedPush ».
- Simple push works by sending a simple PUT request with a version=number payload to the specified HTTPS endpoint every time a relevant message is received: upon receiving such a notification, clients should connect to the MTProto API and fetch updates.
- (Note that the number won't necessarily be incremental in Telegram's implementation, just treat each distinct request as a signal that a new message is waiting to be fetched via MTProto).
- 5 - Ubuntu phone (token for ubuntu push)
- 6 - Blackberry (token for blackberry push)
- 7 - MTProto separate session
- 8 - WNS (windows push)
- 9 - APNS VoIP (token for apple push VoIP)
- 10 - Web push (web push, see below)
- 11 - MPNS VoIP (token for microsoft push VoIP)
- 12 - Tizen (token for tizen push)
- 13 - Huawei push
For 10 web push, the token must be a JSON-encoded object with the following keys:
- endpoint: Absolute URL exposed by the push service where the application server can send push messages
- keys: P-256 elliptic curve Diffie-Hellman parameters in the following object
- p256dh: Base64url-encoded P-256 elliptic curve Diffie-Hellman public key
- auth: Base64url-encoded authentication secret
### Notification encryption
For FCM and APNS VoIP, an optional encryption key used to encrypt push notifications can be passed to account.registerDevice (secret). This key (auth_key) is used to encrypt the payloads using MTProto v2.
The FCM payload will be a JSON payload, containing a p field with the base64url-encoded encrypted MTProto payload. After decryption, the result will be a JSON object, prefixed by a 32-bit little-endian integer with the length of the JSON payload. As usual, make sure to follow all security checks as described in the MTProto docs.
Example implementation.
As mentioned above, payloads can also be encrypted using P-256 Elliptic Curve Diffie-Hellman when using web push.
### Notification structure
An (optionally encrypted) notification is provided as a JSON object in the following format:
Each notification has several parameters that describe it.
- loc_key - Notification type: a string literal in the form /[A-Z_0-9]+/, which summarizes the notification. For example, CHAT_MESSAGE_TEXT.
- loc_args - Notification placeholder arguments: a list or arguments which, when inserted into a template, produce a readable notification.
- custom - Custom parameters to be passed into the application when a notification is opened. Possible fields:
- attachb64 - For notifications about media, base64url-encoded TL-serialization of the corresponding Photo / Document object
- updates - base64url-encoded TL-serialization of the Updates object, currently sent only for PHONE_CALL_REQUEST (with updatePhoneCall inside)
- call_id - Call ID, used in PHONE_CALL_REQUEST
- call_ah - Call access hash, used in PHONE_CALL_REQUEST
- encryption_id - Secret chat id for ENCRYPTION_REQUEST, ENCRYPTION_ACCEPT, ENCRYPTED_MESSAGE
- random_id - Random id for message in ENCRYPTED_MESSAGE
- contact_id - Telegram user identifier of contact that joined Telegram in CONTACT_JOINED
- msg_id - Message ID for new message event or reaction event
- channel_id - Identifier of the channel/supergroup where the event occurred
- chat_id - Identifier of the basic group where the event occurred
- from_id - User ID where the event occurred
- chat_from_broadcast_id - If the group message was sent as a channel, this field will contain the sender channel ID
- chat_from_group_id - If the group message was sent as a supergroup, this field will contain the sender supergroup ID
- chat_from_id - Groups only, message author identifier (ignore if any of chat_from_broadcast_id / chat_from_group_id was present)
- mention - Whether the current user was mentioned/replied to in this new message
- silent - Whether the message was posted silently (no sound should be played for this notification)
- schedule - Whether the message is outgoing and was sent via scheduled messages
- edit_date - When was the message last edited
- top_msg_id - thread_id for new mentions/replies in threads
- sound - The name of an audio file to be played.
- user_id - ID of the account to which the PUSH notification should be delivered, in case of clients with multiple accounts active and running.
- announcement - Roughly equivalent to a message received from the service notifications (Telegram Notifications, id 777000) user, but must be delivered via push notifications, without contacting the API.
### Processing notifications
In principle, data.loc_key, data.custom, and an Internet connection are sufficient to generate a notification. Obviously, if possible, when generating a visual notification you need not use all of the transmitted data and may rely on the information already stored on the client. But if a user or a chat is not cached locally, the values passed in loc_args may also be used. data.user_id is the ID of the account to which the PUSH notification should be delivered, in case of clients with multiple accounts active and running.
### Service notifications
The following notifications can be used to update app settings.
### Possible Notifications
