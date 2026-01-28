# messages.getUnreadReactions
Get unread reactions to messages you sent

```
messages.messages#8c718e87 messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesSlice#762b263d flags:# inexact:flags.1?true count:int next_rate:flags.0?int offset_id_offset:flags.2?int search_flood:flags.3?SearchPostsFlood messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.channelMessages#c776ba4e flags:# inexact:flags.1?true pts:int count:int offset_id_offset:flags.2?int messages:Vector<Message> topics:Vector<ForumTopic> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesNotModified#74535f21 count:int = messages.Messages;
---functions---
messages.getUnreadReactions#bd7f90ac flags:# peer:InputPeer top_msg_id:flags.0?int saved_peer_id:flags.1?InputPeer offset_id:int add_offset:int limit:int max_id:int min_id:int = messages.Messages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | Peer |
| top_msg_id | flags.0?int | If set, considers only reactions to messages within the specified forum topic |
| saved_peer_id | flags.1?InputPeer | If set, must be equal to the ID of a monoforum topic: will affect that topic in the monoforum passed in peer. |
| offset_id | int | Offsets for pagination, for more info click here |
| add_offset | int | Offsets for pagination, for more info click here |
| limit | int | Maximum number of results to return, see pagination |
| max_id | int | Only return reactions for messages up until this message ID |
| min_id | int | Only return reactions for messages starting from this message ID |


## Result
messages.Messages

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

