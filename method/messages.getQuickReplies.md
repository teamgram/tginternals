# messages.getQuickReplies
Fetch basic info about all existing quick reply shortcuts.

```
messages.quickReplies#c68d6695 quick_replies:Vector<QuickReply> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.QuickReplies;
messages.quickRepliesNotModified#5f91eb5b = messages.QuickReplies;
---functions---
messages.getQuickReplies#d483f2a8 hash:long = messages.QuickReplies;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| hash | long | Hash for pagination, generated as specified here » (not the usual algorithm used for hash generation.) |


## Result
messages.QuickReplies

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

