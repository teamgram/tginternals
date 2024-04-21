# messages.sendInlineBotResult
Send a result obtained using messages.getInlineBotResults.

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
messages.sendInlineBotResult#f7bc68ba flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true hide_via:flags.11?true peer:InputPeer reply_to:flags.0?InputReplyTo random_id:long query_id:long id:string schedule_date:flags.10?int send_as:flags.13?InputPeer = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| silent | flags.5?true | Whether to send the message silently (no notification will be triggered on the other client) |
| background | flags.6?true | Whether to send the message in background |
| clear_draft | flags.7?true | Whether to clear the draft |
| hide_via | flags.11?true | Whether to hide the via @botname in the resulting message (only for bot usernames encountered in the config) |
| peer | InputPeer | Destination |
| reply_to | flags.0?InputReplyTo | If set, indicates that the message should be sent in reply to the specified message or story. |
| random_id | long | Random ID to avoid resending the same query |
| query_id | long | Query ID from messages.getInlineBotResults |
| id | string | Result ID from messages.getInlineBotResults |
| schedule_date | flags.10?int | Scheduled message date for scheduled messages |
| send_as | flags.13?InputPeer | Send this message as the specified peer |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 403 | CHAT_GUEST_SEND_FORBIDDEN | You join the discussion group before commenting, see here » for more info. |
| 400 | CHAT_RESTRICTED | You can't send messages in this chat, you were restricted. |
| 403 | CHAT_SEND_AUDIOS_FORBIDDEN | You can't send audio messages in this chat. |
| 403 | CHAT_SEND_GAME_FORBIDDEN | You can't send a game to this chat. |
| 403 | CHAT_SEND_GIFS_FORBIDDEN | You can't send gifs in this chat. |
| 403 | CHAT_SEND_INLINE_FORBIDDEN | You can't send inline messages in this group. |
| 403 | CHAT_SEND_MEDIA_FORBIDDEN | You can't send media in this chat. |
| 403 | CHAT_SEND_PHOTOS_FORBIDDEN | You can't send photos in this chat. |
| 403 | CHAT_SEND_PLAIN_FORBIDDEN | You can't send non-media (text) messages in this chat. |
| 403 | CHAT_SEND_STICKERS_FORBIDDEN | You can't send stickers in this chat. |
| 403 | CHAT_SEND_VOICES_FORBIDDEN | You can't send voice recordings in this chat. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | ENTITY_BOUNDS_INVALID | A specified entity offset or length is invalid, see here » for info on how to properly compute the entity offset/length. |
| 400 | INLINE_RESULT_EXPIRED | The inline query expired. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | MEDIA_EMPTY | The provided media object is invalid. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | QUERY_ID_EMPTY | The query ID is empty. |
| 500 | RANDOM_ID_DUPLICATE | You provided a random ID that was already used. |
| 400 | RESULT_ID_EMPTY | Result ID empty. |
| 400 | RESULT_ID_INVALID | One of the specified result IDs is invalid. |
| 400 | SCHEDULE_DATE_TOO_LATE | You can't schedule a message this far in the future. |
| 400 | SCHEDULE_TOO_MUCH | There are too many scheduled messages. |
| 500 | SEND_MEDIA_INVALID | The specified media is invalid. |
| 420 | SLOWMODE_WAIT_%d | Slowmode is enabled in this chat: wait %d seconds before sending another message to this chat. |
| 400 | TOPIC_DELETED | The specified topic was deleted. |
| 400 | USER_BANNED_IN_CHANNEL | You're banned from sending messages in supergroups/channels. |
| 400 | VOICE_MESSAGES_FORBIDDEN | This user's privacy settings forbid you from sending voice messages. |
| 400 | WEBPAGE_CURL_FAILED | Failure while fetching the webpage with cURL. |
| 400 | WEBPAGE_MEDIA_EMPTY | Webpage media empty. |
| 400 | YOU_BLOCKED_USER | You blocked this user. |

