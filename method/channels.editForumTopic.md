# channels.editForumTopic
Edit forum topic; requires manage_topics rights.

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
channels.editForumTopic#f4dfa185 flags:# channel:InputChannel topic_id:int title:flags.0?string icon_emoji_id:flags.1?long closed:flags.2?Bool hidden:flags.3?Bool = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| channel | InputChannel | Supergroup |
| topic_id | int | Topic ID |
| title | flags.0?string | If present, will update the topic title (maximum UTF-8 length: 128). |
| icon_emoji_id | flags.1?long | If present, updates the custom emoji used as topic icon. Telegram Premium users can use any custom emoji, other users can only use the custom emojis contained in the inputStickerSetEmojiDefaultTopicIcons emoji pack. Pass 0 to switch to the fallback topic icon. |
| closed | flags.2?Bool | If present, will update the open/closed status of the topic. |
| hidden | flags.3?Bool | If present, will hide/unhide the topic (only valid for the "General" topic, id=1). |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_FORUM_MISSING | This supergroup is not a forum. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 403 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | DOCUMENT_INVALID | The specified document is invalid. |
| 400 | GENERAL_MODIFY_ICON_FORBIDDEN | You can't modify the icon of the "General" topic. |
| 400 | TOPIC_CLOSE_SEPARATELY | The close flag cannot be provided together with any of the other flags. |
| 400 | TOPIC_HIDE_SEPARATELY | The hide flag cannot be provided together with any of the other flags. |
| 400 | TOPIC_ID_INVALID | The specified topic ID is invalid. |
| 400 | TOPIC_NOT_MODIFIED | The updated topic info is equal to the current topic info, nothing was changed. |

