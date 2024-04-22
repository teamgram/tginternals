# Min constructors
When receiving said constructors, the client must first check if user or chat object without min flag is already present in local cache. If it is present, then the client should just ignore constructors with min flag and use local one instead.
The rest of the article assumes the client receives a min-constructor and doesn't have the full object in its local cache.
The client must store the context (similar to file references) in which the user/channel was seen. Later, when the client needs to pass the user/channel as input argument (e.g. fetch profile, mute, ban etc), the context is used to generate the input*FromMessage constructor, instead of normal inputUser, inputChannel or inputPeer.
- inputPeerUserFromMessage
- inputPeerChannelFromMessage
- inputUserFromMessage
- inputChannelFromMessage
The access_hash value, if present, is only suitable to use in inputPeerPhotoFileLocation, to directly download the profile pictures of channels and users without having to generate an inputPeer*FromMessage, simply using inputPeer* with the specified access hash.
Usually min constructors are encountered in messages inside of groups or channels.
When a message mentioning (sender, forwarder or forwardee, et cetera) such a user or channel is found, the constuctor must be associated with the message ID of the message and with the chat where the message was seen.
#### Example
Assume a message with id 34 is received from supergroup (actually channel) 123456789.
Said message was sent by from_id 102424212.
The updates container that contained the message has a user with ID 102424212 in the users field, but it has the min flag set, and the provided access_hash may be absent, or otherwise can't be used to generate a typical inputPeerUser constructor to send messages or do other actions.
What the client does is associate 102424212 with the channel 123456789 and message ID 34.
When and if the client will need to interact with user 102424212, it will generate one of the *FromMessage constructors mentioned above, setting:
- msg_id to 34
- peer to the InputPeer associated with channel 123456789
- user_id to 102424212
user_id can also be set to the IDs of users met in the fwd_header (messages forwarded from a user can be used to interact with the original sender, if they don't have privacy settings for forwards enabled).
Users mentioned via messageEntityMentionName in a message can also be used.
The same can be done with min channels.
Example implementations: Telegram for iOS, tdlib.
