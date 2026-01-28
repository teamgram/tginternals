# messages.getScheduledHistory
Get scheduled messages

```
messages.messages#8c718e87 messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesSlice#762b263d flags:# inexact:flags.1?true count:int next_rate:flags.0?int offset_id_offset:flags.2?int search_flood:flags.3?SearchPostsFlood messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.channelMessages#c776ba4e flags:# inexact:flags.1?true pts:int count:int offset_id_offset:flags.2?int messages:Vector<Message> topics:Vector<ForumTopic> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesNotModified#74535f21 count:int = messages.Messages;
---functions---
messages.getScheduledHistory#f516760b peer:InputPeer hash:long = messages.Messages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer |
| hash | long | Hash used for caching, for more info click here. To generate the hash, populate the ids array with the id, edit_date (0 if unedited) and date (in this order) of the previously returned messages (in order, i.e. ids = [id1, (edit_date1 ?? 0), date1, id2, (edit_date2 ?? 0), date2, ...]). |


## Result
messages.Messages

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

