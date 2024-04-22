# Search
Telegram allows applying detailed message filters while looking for messages in chats.
### Search filters
When using messages.search or messages.searchGlobal, a certain message filter may be applied.
This allows the server to filter messages based on a text query, and even on their type, and this feature is often used by graphical clients to implement features like the chat gallery, chat profile pictures and more.
Available filters:
- inputMessagesFilterPhotos - Returns only photos, used for implementing the chat photo gallery, and when scrolling left or right while viewing a photo
- inputMessagesFilterVideo - Returns only videos, used for implementing the chat video gallery, and when scrolling left or right while viewing a video
- inputMessagesFilterPhotoVideo - Return only videos and photos, used for implementing the chat media gallery
- inputMessagesFilterDocument - Return only videos and photos, used for implementing the chat document gallery
- inputMessagesFilterUrl - Return only messages with links, used for implementing the chat link gallery
- inputMessagesFilterGif - Return only GIFs, used for implementing the chat GIF gallery
- inputMessagesFilterVoice - Return only voice messages, used for implementing the chat voice message gallery, and to consecutively play voice messages in a chat
- inputMessagesFilterMusic - Return only music files, used for implementing the chat music gallery
- inputMessagesFilterChatPhotos - Return only chat photos, used to allow scrolling through the profile picture history of a group
- inputMessagesFilterPhoneCalls - Return only phone calls, used with messages.searchGlobal to implement the call tab, with the phone call history
- inputMessagesFilterRoundVoice - Return only round videos and voice messages, used to consecutively play round videos and voice messages in a chat
- inputMessagesFilterRoundVideo - Return only round videos, used to consecutively play round videos in a chat
- inputMessagesFilterMyMentions - Return only messages mentioning me, can be used to display the mention history or, combined with another filter or query, return only messages that satisfy a certain criteria, and contain a mention.
- inputMessagesFilterGeo - Return only geolocations, is used to fetch all recent valid geolocations or live locations sent in a group, to display them all in a single map
- inputMessagesFilterContacts - Return only contacts
- inputMessagesFilterPinned - Returns only pinned messages, used for implementing the pinned message list
The returned messages.Messages constructors contain parameters for pagination, the messages themselves and two offset_id_offset/count parameters that can be used to display a progress/total counter like photo 134 of 200.
For example, when displaying the chat photo gallery, we could display a photo ${offset_id_offset} of ${count} indicator on top.
#### Search counters
Chat counters with filters can also be returned without fetching the actual messages, as seen in the schema above.
