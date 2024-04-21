# messages.addChatUser
Adds a user to a chat and sends a service message on it.

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
messages.addChatUser#f24753e3 chat_id:long user_id:InputUser fwd_limit:int = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| chat_id | long | Chat ID |
| user_id | InputUser | User ID to be added |
| fwd_limit | int | Number of last messages to be forwarded |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_GROUPS_BLOCKED | This bot can't be added to groups. |
| 403 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | USERS_TOO_MUCH | The maximum number of users has been exceeded (to create a chat, for example). |
| 400 | USER_ALREADY_PARTICIPANT | The user is already in the group. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |
| 400 | USER_IS_BLOCKED | You were blocked by this user. |
| 403 | USER_NOT_MUTUAL_CONTACT | The provided user is not a mutual contact. |
| 403 | USER_PRIVACY_RESTRICTED | The user's privacy settings do not allow you to do this. |
| 400 | YOU_BLOCKED_USER | You blocked this user. |

