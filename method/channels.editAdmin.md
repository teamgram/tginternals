# channels.editAdmin
Modify the admin rights of a user in a supergroup/channel.

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
channels.editAdmin#d33c8902 channel:InputChannel user_id:InputUser admin_rights:ChatAdminRights rank:string = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | The supergroup/channel. |
| user_id | InputUser | The ID of the user whose admin rights should be modified |
| admin_rights | ChatAdminRights | The admin rights |
| rank | string | Indicates the role (rank) of the admin in the group: just an arbitrary string |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | ADMINS_TOO_MUCH | There are too many admins. |
| 400 | ADMIN_RANK_EMOJI_NOT_ALLOWED | An admin rank cannot contain emojis. |
| 400 | ADMIN_RANK_INVALID | The specified admin rank is invalid. |
| 400 | BOTS_TOO_MUCH | There are too many bots in this chat/channel. |
| 400 | BOT_CHANNELS_NA | Bots can't edit admin privileges. |
| 400 | BOT_GROUPS_BLOCKED | This bot can't be added to groups. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 403 | CHAT_ADMIN_INVITE_REQUIRED | You do not have the rights to do this. |
| 403 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 406 | FRESH_CHANGE_ADMINS_FORBIDDEN | You were just elected admin, you can't add or modify other admins yet. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 403 | RIGHT_FORBIDDEN | Your admin rights do not allow you to do this. |
| 400 | USERS_TOO_MUCH | The maximum number of users has been exceeded (to create a chat, for example). |
| 400 | USER_BLOCKED | User blocked. |
| 403 | USER_CHANNELS_TOO_MUCH | One of the users you tried to add is already in too many channels/supergroups. |
| 400 | USER_CREATOR | You can't leave this channel, because you're its creator. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |
| 403 | USER_NOT_MUTUAL_CONTACT | The provided user is not a mutual contact. |
| 403 | USER_PRIVACY_RESTRICTED | The user's privacy settings do not allow you to do this. |
| 403 | USER_RESTRICTED | You're spamreported, you can't create channels or chats. |

