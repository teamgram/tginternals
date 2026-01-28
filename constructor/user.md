# user
Indicates info about a certain user.

```
user#20b1422 flags:# self:flags.10?true contact:flags.11?true mutual_contact:flags.12?true deleted:flags.13?true bot:flags.14?true bot_chat_history:flags.15?true bot_nochats:flags.16?true verified:flags.17?true restricted:flags.18?true min:flags.20?true bot_inline_geo:flags.21?true support:flags.23?true scam:flags.24?true apply_min_photo:flags.25?true fake:flags.26?true bot_attach_menu:flags.27?true premium:flags.28?true attach_menu_enabled:flags.29?true flags2:# bot_can_edit:flags2.1?true close_friend:flags2.2?true stories_hidden:flags2.3?true stories_unavailable:flags2.4?true contact_require_premium:flags2.10?true bot_business:flags2.11?true bot_has_main_app:flags2.13?true id:long access_hash:flags.0?long first_name:flags.1?string last_name:flags.2?string username:flags.3?string phone:flags.4?string photo:flags.5?UserProfilePhoto status:flags.6?UserStatus bot_info_version:flags.14?int restriction_reason:flags.18?Vector<RestrictionReason> bot_inline_placeholder:flags.19?string lang_code:flags.22?string emoji_status:flags.30?EmojiStatus usernames:flags2.0?Vector<Username> stories_max_id:flags2.5?int color:flags2.8?PeerColor profile_color:flags2.9?PeerColor bot_active_users:flags2.12?int bot_verification_icon:flags2.14?long send_paid_messages_stars:flags2.15?long = User;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| self | flags.10?true | Whether this user indicates the currently logged in user |
| contact | flags.11?true | Whether this user is a contact When updating the local peer database, do not apply changes to this field if the min flag is set. |
| mutual_contact | flags.12?true | Whether this user is a mutual contact. When updating the local peer database, do not apply changes to this field if the min flag is set. |
| deleted | flags.13?true | Whether the account of this user was deleted. Changes to this flag should invalidate the local userFull cache for this user ID, see here » for more info. |
| bot | flags.14?true | Is this user a bot? Changes to this flag should invalidate the local userFull cache for this user ID, see here » for more info. |
| bot_chat_history | flags.15?true | Can the bot see all messages in groups? |
| bot_nochats | flags.16?true | Can the bot be added to groups? |
| verified | flags.17?true | Whether this user is verified |
| restricted | flags.18?true | Access to this user must be restricted for the reason specified in restriction_reason |
| min | flags.20?true | See min |
| bot_inline_geo | flags.21?true | Whether the bot can request our geolocation in inline mode |
| support | flags.23?true | Whether this is an official support user |
| scam | flags.24?true | This may be a scam user |
| apply_min_photo | flags.25?true | If set and min is set, the value of photo can be used to update the local database, see the documentation of that flag for more info. |
| fake | flags.26?true | If set, this user was reported by many users as a fake or scam user: be careful when interacting with them. |
| bot_attach_menu | flags.27?true | Whether this bot offers an attachment menu web app |
| premium | flags.28?true | Whether this user is a Telegram Premium user Changes to this flag should invalidate the local userFull cache for this user ID, see here » for more info. Changes to this flag if the self flag is set should also trigger the following calls, to refresh the respective caches: - The help.getConfig cache - The messages.getTopReactions cache if the bot flag is not set |
| attach_menu_enabled | flags.29?true | Whether we installed the attachment menu web app offered by this bot. When updating the local peer database, do not apply changes to this field if the min flag is set. |
| flags2 | # | Flags, see TL conditional fields |
| bot_can_edit | flags2.1?true | Whether we can edit the profile picture, name, about text and description of this bot because we own it. When updating the local peer database, do not apply changes to this field if the min flag is set. Changes to this flag (if min is not set) should invalidate the local userFull cache for this user ID. |
| close_friend | flags2.2?true | Whether we marked this user as a close friend, see here » for more info. When updating the local peer database, do not apply changes to this field if the min flag is set. |
| stories_hidden | flags2.3?true | Whether we have hidden » all active stories of this user. When updating the local peer database, do not apply changes to this field if the min flag is set. |
| stories_unavailable | flags2.4?true | No stories from this user are visible. |
| contact_require_premium | flags2.10?true | See here for more info on this flag ». |
| bot_business | flags2.11?true | Whether this bot can be connected to a user as specified here ». |
| bot_has_main_app | flags2.13?true | If set, this bot has configured a Main Mini App ». |
| id | long | ID of the user, see here » for more info and the available ID range. |
| access_hash | flags.0?long | Access hash of the user, see here » for more info. If this flag is set, when updating the local peer database, generate a virtual flag called min_access_hash, which is: - Set to true if min is set AND -- The phone flag is not set OR -- The phone flag is set and the associated phone number string is non-empty - Set to false otherwise. Then, apply both access_hash and min_access_hash to the local database if: - min_access_hash is false OR - min_access_hash is true AND -- There is no locally cached object for this user OR -- There is no access_hash in the local cache OR -- The cached object's min_access_hash is also true If the final merged object stored to the database has the min_access_hash field set to true, the related access_hash is only suitable to use in inputPeerPhotoFileLocation », to directly download the profile pictures of users, everywhere else a inputPeer*FromMessage constructor will have to be generated as specified here ». Bots can also use min access hashes in some conditions, by passing 0 instead of the min access hash. |
| first_name | flags.1?string | First name. When updating the local peer database, apply changes to this field only if: - The min flag is not set OR - The min flag is set AND -- The min flag of the locally cached user entry is set. |
| last_name | flags.2?string | Last name. When updating the local peer database, apply changes to this field only if: - The min flag is not set OR - The min flag is set AND -- The min flag of the locally cached user entry is set. |
| username | flags.3?string | Main active username. When updating the local peer database, apply changes to this field only if: - The min flag is not set OR - The min flag is set AND -- The min flag of the locally cached user entry is set. Changes to this flag should invalidate the local userFull cache for this user ID if the above conditions are respected and the bot_can_edit flag is also set. |
| phone | flags.4?string | Phone number. When updating the local peer database, apply changes to this field only if: - The min flag is not set OR - The min flag is set AND -- The min flag of the locally cached user entry is set. |
| photo | flags.5?UserProfilePhoto | Profile picture of user. When updating the local peer database, apply changes to this field only if: - The min flag is not set OR - The min flag is set AND -- The apply_min_photo flag is set OR -- The min flag of the locally cached user entry is set. |
| status | flags.6?UserStatus | Online status of user. When updating the local peer database, apply changes to this field only if: - The min flag is not set OR - The min flag is set AND -- The min flag of the locally cached user entry is set OR -- The locally cached user entry is equal to userStatusEmpty. |
| bot_info_version | flags.14?int | Version of the bot_info field in userFull, incremented every time it changes. Changes to this flag should invalidate the local userFull cache for this user ID, see here » for more info. |
| restriction_reason | flags.18?Vector<RestrictionReason> | Contains the reason why access to this user must be restricted. |
| bot_inline_placeholder | flags.19?string | Inline placeholder for this inline bot |
| lang_code | flags.22?string | Language code of the user |
| emoji_status | flags.30?EmojiStatus | Emoji status |
| usernames | flags2.0?Vector<Username> | Additional usernames. When updating the local peer database, apply changes to this field only if: - The min flag is not set OR - The min flag is set AND -- The min flag of the locally cached user entry is set. Changes to this flag (if the above conditions are respected) should invalidate the local userFull cache for this user ID. |
| stories_max_id | flags2.5?int | ID of the maximum read story.  When updating the local peer database, do not apply changes to this field if the min flag of the incoming constructor is set. |
| color | flags2.8?PeerColor | The user's accent color. |
| profile_color | flags2.9?PeerColor | The user's profile color. |
| bot_active_users | flags2.12?int | Monthly Active Users (MAU) of this bot (may be absent for small bots). |
| bot_verification_icon | flags2.14?long | Describes a bot verification icon ». |
| send_paid_messages_stars | flags2.15?long | If set, the user has enabled paid messages », we might need to pay the specified amount of Stars to send them messages, depending on the configured exceptions: check userFull.send_paid_messages_stars or users.getRequirementsToContact to see if the currently logged in user actually has to pay or not, see here » for the full flow. |


## Type


## Related pages
