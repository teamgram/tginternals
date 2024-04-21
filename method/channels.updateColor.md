# channels.updateColor
Update the accent color and background custom emoji » of a channel.

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
channels.updateColor#d8aa3671 flags:# for_profile:flags.1?true channel:InputChannel color:flags.2?int background_emoji_id:flags.0?long = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| for_profile | flags.1?true | Whether to change the accent color emoji pattern of the profile page; otherwise, the accent color and emoji pattern of messages will be changed. |
| channel | InputChannel | Channel whose accent color should be changed. |
| color | flags.2?int | ID of the accent color palette » to use (not RGB24, see here » for more info); if not set, the default palette is used. |
| background_emoji_id | flags.0?long | Custom emoji ID used in the accent color pattern. |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOOSTS_REQUIRED | The specified channel must first be boosted by its users in order to perform this action. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |

