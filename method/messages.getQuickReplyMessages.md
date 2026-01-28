# messages.getQuickReplyMessages
Fetch (a subset or all) messages in a quick reply shortcut ».

```
messages.messages#8c718e87 messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesSlice#762b263d flags:# inexact:flags.1?true count:int next_rate:flags.0?int offset_id_offset:flags.2?int search_flood:flags.3?SearchPostsFlood messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.channelMessages#c776ba4e flags:# inexact:flags.1?true pts:int count:int offset_id_offset:flags.2?int messages:Vector<Message> topics:Vector<ForumTopic> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesNotModified#74535f21 count:int = messages.Messages;
---functions---
messages.getQuickReplyMessages#94a495c3 flags:# shortcut_id:int id:flags.0?Vector<int> hash:long = messages.Messages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| shortcut_id | int | Quick reply shortcut ID. |
| id | flags.0?Vector<int> | IDs of the messages to fetch, if empty fetches all of them. |
| hash | long | Hash for pagination, generated as specified here » (not the usual algorithm used for hash generation). |


## Result
messages.Messages

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | SHORTCUT_INVALID | The specified shortcut is invalid. |

