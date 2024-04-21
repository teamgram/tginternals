# messages.sendMessage
Sends a message to a chat

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
messages.sendMessage#280d096f flags:# no_webpage:flags.1?true silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true peer:InputPeer reply_to:flags.0?InputReplyTo message:string random_id:long reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.10?int send_as:flags.13?InputPeer = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| no_webpage | flags.1?true | Set this flag to disable generation of the webpage preview |
| silent | flags.5?true | Send this message silently (no notifications for the receivers) |
| background | flags.6?true | Send this message as background message |
| clear_draft | flags.7?true | Clear the draft field |
| noforwards | flags.14?true | Only for bots, disallows forwarding and saving of the messages, even if the destination chat doesn't have content protection enabled |
| update_stickersets_order | flags.15?true | Whether to move used stickersets to top, see here for more info on this flag » |
| invert_media | flags.16?true | If set, any eventual webpage preview will be shown on top of the message instead of at the bottom. |
| peer | InputPeer | The destination where the message will be sent |
| reply_to | flags.0?InputReplyTo | If set, indicates that the message should be sent in reply to the specified message or story. |
| message | string | The message |
| random_id | long | Unique client message ID required to prevent message resending |
| reply_markup | flags.2?ReplyMarkup | Reply markup for sending bot buttons |
| entities | flags.3?Vector<MessageEntity> | Message entities for sending styled text |
| schedule_date | flags.10?int | Scheduled message date for scheduled messages |
| send_as | flags.13?InputPeer | Send this message as the specified peer |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | ADMIN_RIGHTS_EMPTY | The chatAdminRights constructor passed in keyboardButtonRequestPeer.peer_type.user_admin_rights has no rights set (i.e. flags is 0). |
| 400 | BOT_DOMAIN_INVALID | Bot domain invalid. |
| 400 | BOT_INVALID | This is not a valid bot. |
| 400 | BUTTON_DATA_INVALID | The data of one or more of the buttons you provided is invalid. |
| 400 | BUTTON_TYPE_INVALID | The type of one or more of the buttons you provided is invalid. |
| 400 | BUTTON_URL_INVALID | Button URL invalid. |
| 400 | BUTTON_USER_INVALID | The user_id passed to inputKeyboardButtonUserProfile is invalid! |
| 400 | BUTTON_USER_PRIVACY_RESTRICTED | The privacy setting of the user specified in a inputKeyboardButtonUserProfile button do not allow creating such a button. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 406 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 403 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 403 | CHAT_GUEST_SEND_FORBIDDEN | You join the discussion group before commenting, see here » for more info. |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | CHAT_RESTRICTED | You can't send messages in this chat, you were restricted. |
| 403 | CHAT_SEND_PLAIN_FORBIDDEN | You can't send non-media (text) messages in this chat. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | DOCUMENT_INVALID | The specified document is invalid. |
| 400 | ENCRYPTION_DECLINED | The secret chat was declined. |
| 400 | ENTITIES_TOO_LONG | You provided too many styled message entities. |
| 400 | ENTITY_BOUNDS_INVALID | A specified entity offset or length is invalid, see here » for info on how to properly compute the entity offset/length. |
| 400 | ENTITY_MENTION_USER_INVALID | You mentioned an invalid user. |
| 400 | FROM_MESSAGE_BOT_DISABLED | Bots can't use fromMessage min constructors. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | MESSAGE_EMPTY | The provided message is empty. |
| 400 | MESSAGE_TOO_LONG | The provided message is too long. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 500 | MSG_WAIT_FAILED | A waiting call returned an error. |
| 406 | PAYMENT_UNSUPPORTED | A detailed description of the error will be received separately as described here ». |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | PINNED_DIALOGS_TOO_MUCH | Too many pinned dialogs. |
| 400 | POLL_OPTION_INVALID | Invalid poll option provided. |
| 406 | PRIVACY_PREMIUM_REQUIRED | You need a Telegram Premium subscription to send a message to this user. |
| 500 | RANDOM_ID_DUPLICATE | You provided a random ID that was already used. |
| 400 | REPLY_MARKUP_INVALID | The provided reply markup is invalid. |
| 400 | REPLY_MARKUP_TOO_LONG | The specified reply_markup is too long. |
| 400 | REPLY_TO_INVALID | The specified reply_to field is invalid. |
| 400 | REPLY_TO_USER_INVALID | The replied-to user is invalid. |
| 400 | SCHEDULE_BOT_NOT_ALLOWED | Bots cannot schedule messages. |
| 400 | SCHEDULE_DATE_TOO_LATE | You can't schedule a message this far in the future. |
| 400 | SCHEDULE_STATUS_PRIVATE | Can't schedule until user is online, if the user's last seen timestamp is hidden by their privacy settings. |
| 400 | SCHEDULE_TOO_MUCH | There are too many scheduled messages. |
| 400 | SEND_AS_PEER_INVALID | You can't send messages as the specified peer. |
| 420 | SLOWMODE_WAIT_%d | Slowmode is enabled in this chat: wait %d seconds before sending another message to this chat. |
| 400 | STORY_ID_INVALID | The specified story ID is invalid. |
| 406 | TOPIC_CLOSED | This topic was closed, you can't send messages to it anymore. |
| 406 | TOPIC_DELETED | The specified topic was deleted. |
| 400 | USER_BANNED_IN_CHANNEL | You're banned from sending messages in supergroups/channels. |
| 403 | USER_IS_BLOCKED | You were blocked by this user. |
| 400 | USER_IS_BOT | Bots can't send messages to other bots. |
| 400 | WC_CONVERT_URL_INVALID | WC convert URL invalid. |
| 400 | YOU_BLOCKED_USER | You blocked this user. |

