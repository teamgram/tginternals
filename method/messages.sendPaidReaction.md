# messages.sendPaidReaction
Sends one or more paid Telegram Star reactions », transferring Telegram Stars » to a channel's balance.

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
messages.sendPaidReaction#58bbcb50 flags:# peer:InputPeer msg_id:int count:int random_id:long private:flags.0?PaidReactionPrivacy = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | The channel |
| msg_id | int | The message to react to |
| count | int | The number of stars to send (each will increment the reaction counter by one). |
| random_id | long | Unique client message ID required to prevent message resending. Note: this argument must be composed of a 64-bit integer where the lower 32 bits are random, and the higher 32 bits are equal to the current unixtime, i.e. uint64_t random_id = (time() << 32) | ((uint64_t)random_uint32_t()): this differs from the random_id format of all other methods in the API, which just take 64 random bits. |
| private | flags.0?PaidReactionPrivacy | Each post with star reactions has a leaderboard with the top senders, but users can opt out of appearing there if they prefer more privacy. Not populating this field will use the default reaction privacy, stored on the server and synced to clients using updatePaidReactionPrivacy (see here for more info). |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BALANCE_TOO_LOW | The transaction cannot be completed because the current Telegram Stars balance is too low. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | RANDOM_ID_EMPTY | Random ID empty. |
| 400 | RANDOM_ID_EXPIRED | The specified random_id was expired (most likely it didn't follow the required uint64_t random_id = (time() << 32) | ((uint64_t)random_uint32_t()) format, or the specified time is too far in the past). |
| 400 | REACTIONS_COUNT_INVALID | The specified number of reactions is invalid. |
| 400 | SEND_AS_PEER_INVALID | You can't send messages as the specified peer. |

