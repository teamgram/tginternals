# chatBannedRights
Represents the rights of a normal user in a supergroup/channel/chat. In this case, the flags are inverted: if set, a flag does not allow a user to do X.

```
chatBannedRights#9f120418 flags:# view_messages:flags.0?true send_messages:flags.1?true send_media:flags.2?true send_stickers:flags.3?true send_gifs:flags.4?true send_games:flags.5?true send_inline:flags.6?true embed_links:flags.7?true send_polls:flags.8?true change_info:flags.10?true invite_users:flags.15?true pin_messages:flags.17?true manage_topics:flags.18?true send_photos:flags.19?true send_videos:flags.20?true send_roundvideos:flags.21?true send_audios:flags.22?true send_voices:flags.23?true send_docs:flags.24?true send_plain:flags.25?true until_date:int = ChatBannedRights;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| view_messages | flags.0?true | If set, does not allow a user to view messages in a supergroup/channel/chat |
| send_messages | flags.1?true | If set, does not allow a user to send messages in a supergroup/chat |
| send_media | flags.2?true | If set, does not allow a user to send any media in a supergroup/chat |
| send_stickers | flags.3?true | If set, does not allow a user to send stickers in a supergroup/chat |
| send_gifs | flags.4?true | If set, does not allow a user to send gifs in a supergroup/chat |
| send_games | flags.5?true | If set, does not allow a user to send games in a supergroup/chat |
| send_inline | flags.6?true | If set, does not allow a user to use inline bots in a supergroup/chat. |
| embed_links | flags.7?true | If set, does not allow a user to embed links in the messages of a supergroup/chat |
| send_polls | flags.8?true | If set, does not allow a user to send polls in a supergroup/chat |
| change_info | flags.10?true | If set, does not allow any user to change the description of a supergroup/chat |
| invite_users | flags.15?true | If set, does not allow any user to invite users in a supergroup/chat |
| pin_messages | flags.17?true | If set, does not allow any user to pin messages in a supergroup/chat |
| manage_topics | flags.18?true | If set, does not allow any user to create, delete or modify forum topics ». |
| send_photos | flags.19?true | If set, does not allow a user to send photos in a supergroup/chat. |
| send_videos | flags.20?true | If set, does not allow a user to send videos in a supergroup/chat. |
| send_roundvideos | flags.21?true | If set, does not allow a user to send round videos in a supergroup/chat. |
| send_audios | flags.22?true | If set, does not allow a user to send audio files in a supergroup/chat. |
| send_voices | flags.23?true | If set, does not allow a user to send voice messages in a supergroup/chat. |
| send_docs | flags.24?true | If set, does not allow a user to send documents in a supergroup/chat. |
| send_plain | flags.25?true | If set, does not allow a user to send text messages in a supergroup/chat. |
| until_date | int | Validity of said permissions (it is considered forever any value less then 30 seconds or more then 366 days). |


## Type
ChatBannedRights

## Related pages
