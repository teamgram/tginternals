# messages.importChatInvite
Import a chat invite and join a private chat/supergroup/channel

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
messages.importChatInvite#6c50051c hash:string = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| hash | string | hash from a chat invite deep link |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNELS_TOO_MUCH | You have joined too many channels/supergroups. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_INVALID | Invalid chat. |
| 400 | INVITE_HASH_EMPTY | The invite hash is empty. |
| 406 | INVITE_HASH_EXPIRED | The invite link has expired. |
| 400 | INVITE_HASH_INVALID | The invite hash is invalid. |
| 400 | INVITE_REQUEST_SENT | You have successfully requested to join this chat or channel. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | USERS_TOO_MUCH | The maximum number of users has been exceeded (to create a chat, for example). |
| 400 | USER_ALREADY_PARTICIPANT | The user is already in the group. |
| 400 | USER_CHANNELS_TOO_MUCH | One of the users you tried to add is already in too many channels/supergroups. |

