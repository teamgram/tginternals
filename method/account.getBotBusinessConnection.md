# account.getBotBusinessConnection
Bots may invoke this method to re-fetch the updateBotBusinessConnect constructor associated with a specific business connection_id, see here » for more info on connected business bots.
This is needed for example for freshly logged in bots that are receiving some updateBotNewBusinessMessage, etc. updates because some users have already connected to the bot before it could login.
In this case, the bot is receiving messages from the business connection, but it hasn't cached the associated updateBotBusinessConnect with info about the connection (can it reply to messages? etc.) yet, and cannot receive the old ones because they were sent when the bot wasn't logged into the session yet.
This method can be used to fetch info about a not-yet-cached business connection, and should not be invoked if the info is already cached or to fetch changes, as eventual changes will automatically be sent as new updateBotBusinessConnect updates to the bot using the usual update delivery methods ».

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
account.getBotBusinessConnection#76a86270 connection_id:string = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| connection_id | string | Business connection ID ». |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CONNECTION_ID_INVALID | The specified connection ID is invalid. |

