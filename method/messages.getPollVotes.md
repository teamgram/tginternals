# messages.getPollVotes
Get poll results for non-anonymous polls

```
messages.votesList#4899484e flags:# count:int votes:Vector<MessagePeerVote> chats:Vector<Chat> users:Vector<User> next_offset:flags.0?string = messages.VotesList;
---functions---
messages.getPollVotes#b86e380e flags:# peer:InputPeer id:int option:flags.0?bytes offset:flags.1?string limit:int = messages.VotesList;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | Chat where the poll was sent |
| id | int | Message ID |
| option | flags.0?bytes | Get only results for the specified poll option |
| offset | flags.1?string | Offset for results, taken from the next_offset field of messages.votesList, initially an empty string. Note: if no more results are available, the method call will return an empty next_offset; thus, avoid providing the next_offset returned in messages.votesList if it is empty, to avoid an infinite loop. |
| limit | int | Number of results to return |


## Result
messages.VotesList

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | BROADCAST_FORBIDDEN | Channel poll voters and reactions cannot be fetched to prevent deanonymization. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 403 | POLL_VOTE_REQUIRED | Cast a vote in the poll before calling this method. |

