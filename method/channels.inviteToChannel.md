# channels.inviteToChannel
Invite users to a channel/supergroup

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
channels.inviteToChannel#199f3a6c channel:InputChannel users:Vector<InputUser> = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | Channel/supergroup |
| users | Vector<InputUser> | Users to invite |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOTS_TOO_MUCH | There are too many bots in this chat/channel. |
| 400 | BOT_GROUPS_BLOCKED | This bot can't be added to groups. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 406 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 403 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | CHAT_INVALID | Invalid chat. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | USERS_TOO_MUCH | The maximum number of users has been exceeded (to create a chat, for example). |
| 400 | USER_BANNED_IN_CHANNEL | You're banned from sending messages in supergroups/channels. |
| 400 | USER_BLOCKED | User blocked. |
| 400 | USER_BOT | Bots can only be admins in channels. |
| 403 | USER_CHANNELS_TOO_MUCH | One of the users you tried to add is already in too many channels/supergroups. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |
| 400 | USER_KICKED | This user was kicked from this supergroup/channel. |
| 403 | USER_NOT_MUTUAL_CONTACT | The provided user is not a mutual contact. |
| 403 | USER_PRIVACY_RESTRICTED | The user's privacy settings do not allow you to do this. |

