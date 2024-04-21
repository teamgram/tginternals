# channels.createChannel
Create a supergroup/channel.

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
channels.createChannel#91006707 flags:# broadcast:flags.0?true megagroup:flags.1?true for_import:flags.3?true forum:flags.5?true title:string about:string geo_point:flags.2?InputGeoPoint address:flags.2?string ttl_period:flags.4?int = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| broadcast | flags.0?true | Whether to create a channel |
| megagroup | flags.1?true | Whether to create a supergroup |
| for_import | flags.3?true | Whether the supergroup is being created to import messages from a foreign chat service using messages.initHistoryImport |
| forum | flags.5?true | Whether to create a forum |
| title | string | Channel title |
| about | string | Channel description |
| geo_point | flags.2?InputGeoPoint | Geogroup location, see here » for more info on geogroups. |
| address | flags.2?string | Geogroup address, see here » for more info on geogroups. |
| ttl_period | flags.4?int | Time-to-live of all messages that will be sent in the supergroup: once message.date+message.ttl_period === time(), the message will be deleted on the server, and must be deleted locally as well. You can use messages.setDefaultHistoryTTL to edit this value later. |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | ADDRESS_INVALID | The specified geopoint address is invalid. |
| 400 | CHANNELS_ADMIN_LOCATED_TOO_MUCH | The user has reached the limit of public geogroups. |
| 400 | CHANNELS_TOO_MUCH | You have joined too many channels/supergroups. |
| 400 | CHAT_ABOUT_TOO_LONG | Chat about too long. |
| 500 | CHAT_INVALID | Invalid chat. |
| 400 | CHAT_TITLE_EMPTY | No chat title provided. |
| 400 | TTL_PERIOD_INVALID | The specified TTL period is invalid. |
| 406 | USER_RESTRICTED | You're spamreported, you can't create channels or chats. |

