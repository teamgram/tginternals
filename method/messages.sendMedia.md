# messages.sendMedia
Send a media

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
messages.sendMedia#72ccc23d flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true peer:InputPeer reply_to:flags.0?InputReplyTo media:InputMedia message:string random_id:long reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.10?int send_as:flags.13?InputPeer = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| silent | flags.5?true | Send message silently (no notification should be triggered) |
| background | flags.6?true | Send message in background |
| clear_draft | flags.7?true | Clear the draft |
| noforwards | flags.14?true | Only for bots, disallows forwarding and saving of the messages, even if the destination chat doesn't have content protection enabled |
| update_stickersets_order | flags.15?true | Whether to move used stickersets to top, see here for more info on this flag » |
| invert_media | flags.16?true | If set, any eventual webpage preview will be shown on top of the message instead of at the bottom. |
| peer | InputPeer | Destination |
| reply_to | flags.0?InputReplyTo | If set, indicates that the message should be sent in reply to the specified message or story. |
| media | InputMedia | Attached media |
| message | string | Caption |
| random_id | long | Random ID to avoid resending the same message |
| reply_markup | flags.2?ReplyMarkup | Reply markup for bot keyboards |
| entities | flags.3?Vector<MessageEntity> | Message entities for styled text |
| schedule_date | flags.10?int | Scheduled message date for scheduled messages |
| send_as | flags.13?InputPeer | Send this message as the specified peer |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_PAYMENTS_DISABLED | Please enable bot payments in botfather before calling this method. |
| 400 | BROADCAST_PUBLIC_VOTERS_FORBIDDEN | You can't forward polls with public voters. |
| 400 | BUTTON_DATA_INVALID | The data of one or more of the buttons you provided is invalid. |
| 400 | BUTTON_TYPE_INVALID | The type of one or more of the buttons you provided is invalid. |
| 400 | BUTTON_URL_INVALID | Button URL invalid. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 406 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 403 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | CHAT_FORWARDS_RESTRICTED | You can't forward messages from a protected chat. |
| 403 | CHAT_GUEST_SEND_FORBIDDEN | You join the discussion group before commenting, see here » for more info. |
| 400 | CHAT_RESTRICTED | You can't send messages in this chat, you were restricted. |
| 403 | CHAT_SEND_AUDIOS_FORBIDDEN | You can't send audio messages in this chat. |
| 403 | CHAT_SEND_DOCS_FORBIDDEN | You can't send documents in this chat. |
| 403 | CHAT_SEND_GIFS_FORBIDDEN | You can't send gifs in this chat. |
| 403 | CHAT_SEND_MEDIA_FORBIDDEN | You can't send media in this chat. |
| 403 | CHAT_SEND_PHOTOS_FORBIDDEN | You can't send photos in this chat. |
| 403 | CHAT_SEND_PLAIN_FORBIDDEN | You can't send non-media (text) messages in this chat. |
| 403 | CHAT_SEND_POLL_FORBIDDEN | You can't send polls in this chat. |
| 403 | CHAT_SEND_STICKERS_FORBIDDEN | You can't send stickers in this chat. |
| 403 | CHAT_SEND_VIDEOS_FORBIDDEN | You can't send videos in this chat. |
| 403 | CHAT_SEND_VOICES_FORBIDDEN | You can't send voice recordings in this chat. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | CURRENCY_TOTAL_AMOUNT_INVALID | The total amount of all prices is invalid. |
| 400 | DOCUMENT_INVALID | The specified document is invalid. |
| 400 | EMOTICON_INVALID | The specified emoji is invalid. |
| 400 | ENTITY_BOUNDS_INVALID | A specified entity offset or length is invalid, see here » for info on how to properly compute the entity offset/length. |
| 400 | EXTERNAL_URL_INVALID | External URL invalid. |
| 400 | FILE_PARTS_INVALID | The number of file parts is invalid. |
| 400 | FILE_PART_LENGTH_INVALID | The length of a file part is invalid. |
| 400 | FILE_REFERENCE_EMPTY | An empty file reference was specified. |
| 400 | FILE_REFERENCE_EXPIRED | File reference expired, it must be refetched as described in the documentation. |
| 400 | GAME_BOT_INVALID | Bots can't send another bot's game. |
| 400 | IMAGE_PROCESS_FAILED | Failure while processing image. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | MD5_CHECKSUM_INVALID | The MD5 checksums do not match. |
| 400 | MEDIA_CAPTION_TOO_LONG | The caption is too long. |
| 400 | MEDIA_EMPTY | The provided media object is invalid. |
| 400 | MEDIA_INVALID | Media invalid. |
| 400 | MESSAGE_EMPTY | The provided message is empty. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PAYMENT_PROVIDER_INVALID | The specified payment provider is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | PHOTO_EXT_INVALID | The extension of the photo is invalid. |
| 400 | PHOTO_INVALID_DIMENSIONS | The photo dimensions are invalid. |
| 400 | PHOTO_SAVE_FILE_INVALID | Internal issues, try again later. |
| 400 | POLL_ANSWERS_INVALID | Invalid poll answers were provided. |
| 400 | POLL_ANSWER_INVALID | One of the poll answers is not acceptable. |
| 400 | POLL_OPTION_DUPLICATE | Duplicate poll options provided. |
| 400 | POLL_OPTION_INVALID | Invalid poll option provided. |
| 400 | POLL_QUESTION_INVALID | One of the poll questions is not acceptable. |
| 403 | PREMIUM_ACCOUNT_REQUIRED | A premium account is required to execute this action. |
| 400 | QUIZ_CORRECT_ANSWERS_EMPTY | No correct quiz answer was specified. |
| 400 | QUIZ_CORRECT_ANSWERS_TOO_MUCH | You specified too many correct answers in a quiz, quizzes can only have one right answer! |
| 400 | QUIZ_CORRECT_ANSWER_INVALID | An invalid value was provided to the correct_answers field. |
| 400 | QUIZ_MULTIPLE_INVALID | Quizzes can't have the multiple_choice flag set! |
| 500 | RANDOM_ID_DUPLICATE | You provided a random ID that was already used. |
| 400 | REPLY_MARKUP_BUY_EMPTY | Reply markup for buy button empty. |
| 400 | REPLY_MARKUP_INVALID | The provided reply markup is invalid. |
| 400 | REPLY_MARKUP_TOO_LONG | The specified reply_markup is too long. |
| 400 | SCHEDULE_BOT_NOT_ALLOWED | Bots cannot schedule messages. |
| 400 | SCHEDULE_DATE_TOO_LATE | You can't schedule a message this far in the future. |
| 400 | SCHEDULE_TOO_MUCH | There are too many scheduled messages. |
| 400 | SEND_AS_PEER_INVALID | You can't send messages as the specified peer. |
| 420 | SLOWMODE_WAIT_%d | Slowmode is enabled in this chat: wait %d seconds before sending another message to this chat. |
| 406 | TOPIC_CLOSED | This topic was closed, you can't send messages to it anymore. |
| 406 | TOPIC_DELETED | The specified topic was deleted. |
| 400 | TTL_MEDIA_INVALID | Invalid media Time To Live was provided. |
| 400 | USER_BANNED_IN_CHANNEL | You're banned from sending messages in supergroups/channels. |
| 403 | USER_IS_BLOCKED | You were blocked by this user. |
| 400 | USER_IS_BOT | Bots can't send messages to other bots. |
| 400 | VIDEO_CONTENT_TYPE_INVALID | The video's content type is invalid. |
| 400 | VOICE_MESSAGES_FORBIDDEN | This user's privacy settings forbid you from sending voice messages. |
| 400 | WEBDOCUMENT_MIME_INVALID | Invalid webdocument mime type provided. |
| 400 | WEBPAGE_CURL_FAILED | Failure while fetching the webpage with cURL. |
| 400 | WEBPAGE_MEDIA_EMPTY | Webpage media empty. |
| 400 | WEBPAGE_NOT_FOUND | A preview for the specified webpage url could not be generated. |
| 400 | WEBPAGE_URL_INVALID | The specified webpage url is invalid. |
| 400 | YOU_BLOCKED_USER | You blocked this user. |

