# messages.sendMultiMedia
Send an album or grouped media

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
messages.sendMultiMedia#456e8987 flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true peer:InputPeer reply_to:flags.0?InputReplyTo multi_media:Vector<InputSingleMedia> schedule_date:flags.10?int send_as:flags.13?InputPeer = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| silent | flags.5?true | Whether to send the album silently (no notification triggered) |
| background | flags.6?true | Send in background? |
| clear_draft | flags.7?true | Whether to clear drafts |
| noforwards | flags.14?true | Only for bots, disallows forwarding and saving of the messages, even if the destination chat doesn't have content protection enabled |
| update_stickersets_order | flags.15?true | Whether to move used stickersets to top, see here for more info on this flag » |
| invert_media | flags.16?true | If set, any eventual webpage preview will be shown on top of the message instead of at the bottom. |
| peer | InputPeer | The destination chat |
| reply_to | flags.0?InputReplyTo | If set, indicates that the message should be sent in reply to the specified message or story. |
| multi_media | Vector<InputSingleMedia> | The medias to send: note that they must be separately uploaded using messages.uploadMedia first, using raw inputMediaUploaded* constructors is not supported. |
| schedule_date | flags.10?int | Scheduled message date for scheduled messages |
| send_as | flags.13?InputPeer | Send this message as the specified peer |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | CHAT_FORWARDS_RESTRICTED | You can't forward messages from a protected chat. |
| 403 | CHAT_SEND_MEDIA_FORBIDDEN | You can't send media in this chat. |
| 403 | CHAT_SEND_PHOTOS_FORBIDDEN | You can't send photos in this chat. |
| 403 | CHAT_SEND_VIDEOS_FORBIDDEN | You can't send videos in this chat. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | ENTITY_BOUNDS_INVALID | A specified entity offset or length is invalid, see here » for info on how to properly compute the entity offset/length. |
| 400 | MEDIA_CAPTION_TOO_LONG | The caption is too long. |
| 400 | MEDIA_EMPTY | The provided media object is invalid. |
| 400 | MEDIA_INVALID | Media invalid. |
| 400 | MULTI_MEDIA_TOO_LONG | Too many media files for album. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 500 | RANDOM_ID_DUPLICATE | You provided a random ID that was already used. |
| 400 | RANDOM_ID_EMPTY | Random ID empty. |
| 400 | SCHEDULE_DATE_TOO_LATE | You can't schedule a message this far in the future. |
| 400 | SCHEDULE_TOO_MUCH | There are too many scheduled messages. |
| 400 | SEND_AS_PEER_INVALID | You can't send messages as the specified peer. |
| 420 | SLOWMODE_WAIT_%d | Slowmode is enabled in this chat: wait %d seconds before sending another message to this chat. |
| 400 | TOPIC_CLOSED | This topic was closed, you can't send messages to it anymore. |
| 400 | TOPIC_DELETED | The specified topic was deleted. |
| 400 | USER_BANNED_IN_CHANNEL | You're banned from sending messages in supergroups/channels. |

