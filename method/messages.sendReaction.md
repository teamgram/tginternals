# messages.sendReaction
React to message.

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
messages.sendReaction#d30d78d4 flags:# big:flags.1?true add_to_recent:flags.2?true peer:InputPeer msg_id:int reaction:flags.0?Vector<Reaction> = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| big | flags.1?true | Whether a bigger and longer reaction should be shown |
| add_to_recent | flags.2?true | Whether to add this reaction to the recent reactions list ». |
| peer | InputPeer | Peer |
| msg_id | int | Message ID to react to |
| reaction | flags.0?Vector<Reaction> | A list of reactions |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | ANONYMOUS_REACTIONS_DISABLED | Sorry, anonymous administrators cannot leave reactions or participate in polls. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | CUSTOM_REACTIONS_TOO_MANY | Too many custom reactions were specified. |
| 400 | DOCUMENT_INVALID | The specified document is invalid. |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | MESSAGE_NOT_MODIFIED | The provided message data is identical to the previous message data, the message wasn't modified. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 403 | PREMIUM_ACCOUNT_REQUIRED | A premium account is required to execute this action. |
| 400 | REACTIONS_TOO_MANY | The message already has exactly reactions_uniq_max reaction emojis, you can't react with a new emoji, see the docs for more info ». |
| 400 | REACTION_EMPTY | Empty reaction provided. |
| 400 | REACTION_INVALID | The specified reaction is invalid. |
| 400 | USER_BANNED_IN_CHANNEL | You're banned from sending messages in supergroups/channels. |

