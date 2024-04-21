# messages.editMessage
Edit message

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
messages.editMessage#48f71778 flags:# no_webpage:flags.1?true invert_media:flags.16?true peer:InputPeer id:int message:flags.11?string media:flags.14?InputMedia reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.15?int = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| no_webpage | flags.1?true | Disable webpage preview |
| invert_media | flags.16?true | If set, any eventual webpage preview will be shown on top of the message instead of at the bottom. |
| peer | InputPeer | Where was the message sent |
| id | int | ID of the message to edit |
| message | flags.11?string | New message |
| media | flags.14?InputMedia | New attached media |
| reply_markup | flags.2?ReplyMarkup | Reply markup for inline keyboards |
| entities | flags.3?Vector<MessageEntity> | Message entities for styled text |
| schedule_date | flags.15?int | Scheduled message date for scheduled messages |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_DOMAIN_INVALID | Bot domain invalid. |
| 400 | BOT_INVALID | This is not a valid bot. |
| 400 | BUTTON_DATA_INVALID | The data of one or more of the buttons you provided is invalid. |
| 400 | BUTTON_TYPE_INVALID | The type of one or more of the buttons you provided is invalid. |
| 400 | BUTTON_URL_INVALID | Button URL invalid. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 406 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 403 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | CHAT_FORWARDS_RESTRICTED | You can't forward messages from a protected chat. |
| 403 | CHAT_SEND_GIFS_FORBIDDEN | You can't send gifs in this chat. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | DOCUMENT_INVALID | The specified document is invalid. |
| 400 | ENTITIES_TOO_LONG | You provided too many styled message entities. |
| 400 | ENTITY_BOUNDS_INVALID | A specified entity offset or length is invalid, see here » for info on how to properly compute the entity offset/length. |
| 400 | FILE_PARTS_INVALID | The number of file parts is invalid. |
| 400 | IMAGE_PROCESS_FAILED | Failure while processing image. |
| 403 | INLINE_BOT_REQUIRED | Only the inline bot can edit message. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | MEDIA_CAPTION_TOO_LONG | The caption is too long. |
| 400 | MEDIA_EMPTY | The provided media object is invalid. |
| 400 | MEDIA_GROUPED_INVALID | You tried to send media of different types in an album. |
| 400 | MEDIA_INVALID | Media invalid. |
| 400 | MEDIA_NEW_INVALID | The new media is invalid. |
| 400 | MEDIA_PREV_INVALID | Previous media invalid. |
| 400 | MEDIA_TTL_INVALID | The specified media TTL is invalid. |
| 403 | MESSAGE_AUTHOR_REQUIRED | Message author required. |
| 400 | MESSAGE_EDIT_TIME_EXPIRED | You can't edit this message anymore, too much time has passed since its creation. |
| 400 | MESSAGE_EMPTY | The provided message is empty. |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | MESSAGE_NOT_MODIFIED | The provided message data is identical to the previous message data, the message wasn't modified. |
| 400 | MESSAGE_TOO_LONG | The provided message is too long. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 500 | MSG_WAIT_FAILED | A waiting call returned an error. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | REPLY_MARKUP_INVALID | The provided reply markup is invalid. |
| 400 | REPLY_MARKUP_TOO_LONG | The specified reply_markup is too long. |
| 400 | SCHEDULE_DATE_INVALID | Invalid schedule date provided. |
| 400 | USER_BANNED_IN_CHANNEL | You're banned from sending messages in supergroups/channels. |

