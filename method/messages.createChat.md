# messages.createChat
Creates a new chat.

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
messages.createChat#34a818 flags:# users:Vector<InputUser> title:string ttl_period:flags.0?int = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| users | Vector<InputUser> | List of user IDs to be invited |
| title | string | Chat name |
| ttl_period | flags.0?int | Time-to-live of all messages that will be sent in the chat: once message.date+message.ttl_period === time(), the message will be deleted on the server, and must be deleted locally as well. You can use messages.setDefaultHistoryTTL to edit this value later. |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 500 | CHAT_ID_GENERATE_FAILED | Failure while generating the chat ID. |
| 400 | CHAT_INVALID | Invalid chat. |
| 400 | CHAT_TITLE_EMPTY | No chat title provided. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | TTL_PERIOD_INVALID | The specified TTL period is invalid. |
| 400 | USERS_TOO_FEW | Not enough users (to create a chat, for example). |
| 406 | USER_RESTRICTED | You're spamreported, you can't create channels or chats. |

