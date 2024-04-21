# messages.searchSentMedia
View and search recently sent media.
This method does not support pagination.

```
messages.messages#8c718e87 messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesSlice#3a54685e flags:# inexact:flags.1?true count:int next_rate:flags.0?int offset_id_offset:flags.2?int messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.channelMessages#c776ba4e flags:# inexact:flags.1?true pts:int count:int offset_id_offset:flags.2?int messages:Vector<Message> topics:Vector<ForumTopic> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesNotModified#74535f21 count:int = messages.Messages;
---functions---
messages.searchSentMedia#107e31a0 q:string filter:MessagesFilter limit:int = messages.Messages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| q | string | Optional search query |
| filter | MessagesFilter | Message filter |
| limit | int | Maximum number of results to return (max 100). |


## Result
messages.Messages

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | FILTER_NOT_SUPPORTED | The specified filter cannot be used in this context. |

