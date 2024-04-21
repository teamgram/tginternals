# messages.forwardMessages
Forwards messages by their IDs.

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
messages.forwardMessages#c661bbc4 flags:# silent:flags.5?true background:flags.6?true with_my_score:flags.8?true drop_author:flags.11?true drop_media_captions:flags.12?true noforwards:flags.14?true from_peer:InputPeer id:Vector<int> random_id:Vector<long> to_peer:InputPeer top_msg_id:flags.9?int schedule_date:flags.10?int send_as:flags.13?InputPeer = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| silent | flags.5?true | Whether to send messages silently (no notification will be triggered on the destination clients) |
| background | flags.6?true | Whether to send the message in background |
| with_my_score | flags.8?true | When forwarding games, whether to include your score in the game |
| drop_author | flags.11?true | Whether to forward messages without quoting the original author |
| drop_media_captions | flags.12?true | Whether to strip captions from media |
| noforwards | flags.14?true | Only for bots, disallows further re-forwarding and saving of the messages, even if the destination chat doesn't have content protection enabled |
| from_peer | InputPeer | Source of messages |
| id | Vector<int> | IDs of messages |
| random_id | Vector<long> | Random ID to prevent resending of messages |
| to_peer | InputPeer | Destination peer |
| top_msg_id | flags.9?int | Destination forum topic |
| schedule_date | flags.10?int | Scheduled message date for scheduled messages |
| send_as | flags.13?InputPeer | Forward the messages as the specified peer |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BROADCAST_PUBLIC_VOTERS_FORBIDDEN | You can't forward polls with public voters. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 406 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 403 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 406 | CHAT_FORWARDS_RESTRICTED | You can't forward messages from a protected chat. |
| 403 | CHAT_GUEST_SEND_FORBIDDEN | You join the discussion group before commenting, see here » for more info. |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | CHAT_RESTRICTED | You can't send messages in this chat, you were restricted. |
| 403 | CHAT_SEND_AUDIOS_FORBIDDEN | You can't send audio messages in this chat. |
| 403 | CHAT_SEND_DOCS_FORBIDDEN | You can't send documents in this chat. |
| 403 | CHAT_SEND_GAME_FORBIDDEN | You can't send a game to this chat. |
| 403 | CHAT_SEND_GIFS_FORBIDDEN | You can't send gifs in this chat. |
| 403 | CHAT_SEND_MEDIA_FORBIDDEN | You can't send media in this chat. |
| 403 | CHAT_SEND_PHOTOS_FORBIDDEN | You can't send photos in this chat. |
| 403 | CHAT_SEND_PLAIN_FORBIDDEN | You can't send non-media (text) messages in this chat. |
| 403 | CHAT_SEND_POLL_FORBIDDEN | You can't send polls in this chat. |
| 403 | CHAT_SEND_STICKERS_FORBIDDEN | You can't send stickers in this chat. |
| 403 | CHAT_SEND_VIDEOS_FORBIDDEN | You can't send videos in this chat. |
| 403 | CHAT_SEND_VOICES_FORBIDDEN | You can't send voice recordings in this chat. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | GROUPED_MEDIA_INVALID | Invalid grouped media. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | MEDIA_EMPTY | The provided media object is invalid. |
| 400 | MESSAGE_IDS_EMPTY | No message ids were provided. |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 406 | PAYMENT_UNSUPPORTED | A detailed description of the error will be received separately as described here ». |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | QUIZ_ANSWER_MISSING | You can forward a quiz while hiding the original author only after choosing an option in the quiz. |
| 500 | RANDOM_ID_DUPLICATE | You provided a random ID that was already used. |
| 400 | RANDOM_ID_INVALID | A provided random ID is invalid. |
| 400 | SCHEDULE_BOT_NOT_ALLOWED | Bots cannot schedule messages. |
| 400 | SCHEDULE_DATE_TOO_LATE | You can't schedule a message this far in the future. |
| 400 | SCHEDULE_TOO_MUCH | There are too many scheduled messages. |
| 400 | SEND_AS_PEER_INVALID | You can't send messages as the specified peer. |
| 400 | SLOWMODE_MULTI_MSGS_DISABLED | Slowmode is enabled, you cannot forward multiple messages to this group. |
| 420 | SLOWMODE_WAIT_%d | Slowmode is enabled in this chat: wait %d seconds before sending another message to this chat. |
| 406 | TOPIC_CLOSED | This topic was closed, you can't send messages to it anymore. |
| 406 | TOPIC_DELETED | The specified topic was deleted. |
| 400 | USER_BANNED_IN_CHANNEL | You're banned from sending messages in supergroups/channels. |
| 403 | USER_IS_BLOCKED | You were blocked by this user. |
| 400 | USER_IS_BOT | Bots can't send messages to other bots. |
| 403 | VOICE_MESSAGES_FORBIDDEN | This user's privacy settings forbid you from sending voice messages. |
| 400 | YOU_BLOCKED_USER | You blocked this user. |

