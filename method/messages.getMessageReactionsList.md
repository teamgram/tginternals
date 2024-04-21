# messages.getMessageReactionsList
Get message reaction list, along with the sender of each reaction.

```
messages.messageReactionsList#31bd492d flags:# count:int reactions:Vector<MessagePeerReaction> chats:Vector<Chat> users:Vector<User> next_offset:flags.0?string = messages.MessageReactionsList;
---functions---
messages.getMessageReactionsList#461b3f48 flags:# peer:InputPeer id:int reaction:flags.0?Reaction offset:flags.1?string limit:int = messages.MessageReactionsList;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | Peer |
| id | int | Message ID |
| reaction | flags.0?Reaction | Get only reactions of this type |
| offset | flags.1?string | Offset for pagination (taken from the next_offset field of the returned messages.MessageReactionsList); empty in the first request. |
| limit | int | Maximum number of results to return, see pagination |


## Result
messages.MessageReactionsList

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | BROADCAST_FORBIDDEN | Channel poll voters and reactions cannot be fetched to prevent deanonymization. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |

