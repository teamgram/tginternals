# messages.votesList
How users voted in a poll

```
messages.votesList#4899484e flags:# count:int votes:Vector<MessagePeerVote> chats:Vector<Chat> users:Vector<User> next_offset:flags.0?string = messages.VotesList;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| count | int | Total number of votes for all options (or only for the chosen option, if provided to messages.getPollVotes) |
| votes | Vector<MessagePeerVote> | Vote info for each user |
| chats | Vector<Chat> | Mentioned chats |
| users | Vector<User> | Info about users that voted in the poll |
| next_offset | flags.0?string | Offset to use with the next messages.getPollVotes request, empty string if no more results are available. |


## Type
messages.VotesList

## Related pages
