# messages.getSavedHistory
Returns saved messages » forwarded from a specific peer

```
messages.messages#8c718e87 messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesSlice#3a54685e flags:# inexact:flags.1?true count:int next_rate:flags.0?int offset_id_offset:flags.2?int messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.channelMessages#c776ba4e flags:# inexact:flags.1?true pts:int count:int offset_id_offset:flags.2?int messages:Vector<Message> topics:Vector<ForumTopic> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesNotModified#74535f21 count:int = messages.Messages;
---functions---
messages.getSavedHistory#3d9a414d peer:InputPeer offset_id:int offset_date:int add_offset:int limit:int max_id:int min_id:int hash:long = messages.Messages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Target peer |
| offset_id | int | Only return messages starting from the specified message ID |
| offset_date | int | Only return messages sent before the specified date |
| add_offset | int | Number of list elements to be skipped, negative values are also accepted. |
| limit | int | Number of results to return |
| max_id | int | If a positive value was transferred, the method will return only messages with IDs less than max_id |
| min_id | int | If a positive value was transferred, the method will return only messages with IDs more than min_id |
| hash | long | Result hash |


## Result
messages.Messages

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

