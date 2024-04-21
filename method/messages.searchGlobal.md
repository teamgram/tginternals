# messages.searchGlobal
Search for messages and peers globally

```
messages.messages#8c718e87 messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesSlice#3a54685e flags:# inexact:flags.1?true count:int next_rate:flags.0?int offset_id_offset:flags.2?int messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.channelMessages#c776ba4e flags:# inexact:flags.1?true pts:int count:int offset_id_offset:flags.2?int messages:Vector<Message> topics:Vector<ForumTopic> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesNotModified#74535f21 count:int = messages.Messages;
---functions---
messages.searchGlobal#4bc6589a flags:# broadcasts_only:flags.1?true folder_id:flags.0?int q:string filter:MessagesFilter min_date:int max_date:int offset_rate:int offset_peer:InputPeer offset_id:int limit:int = messages.Messages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| folder_id | flags.0?int | Peer folder ID, for more info click here |
| q | string | Query |
| filter | MessagesFilter | Global search filter |
| min_date | int | If a positive value was specified, the method will return only messages with date bigger than min_date |
| max_date | int | If a positive value was transferred, the method will return only messages with date smaller than max_date |
| offset_rate | int | Initially 0, then set to the next_rate parameter of messages.messagesSlice |
| offset_peer | InputPeer | Offsets for pagination, for more info click here |
| offset_id | int | Offsets for pagination, for more info click here |
| limit | int | Offsets for pagination, for more info click here |


## Result
messages.Messages

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | FOLDER_ID_INVALID | Invalid folder ID. |
| 400 | SEARCH_QUERY_EMPTY | The search query is empty. |

