# poll
Poll

```
poll#86e18161 id:long flags:# closed:flags.0?true public_voters:flags.1?true multiple_choice:flags.2?true quiz:flags.3?true question:string answers:Vector<PollAnswer> close_period:flags.4?int close_date:flags.5?int = Poll;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | long | ID of the poll |
| flags | # | Flags, see TL conditional fields |
| closed | flags.0?true | Whether the poll is closed and doesn't accept any more answers |
| public_voters | flags.1?true | Whether cast votes are publicly visible to all users (non-anonymous poll) |
| multiple_choice | flags.2?true | Whether multiple options can be chosen as answer |
| quiz | flags.3?true | Whether this is a quiz (with wrong and correct answers, results shown in the return type) |
| question | string | The question of the poll |
| answers | Vector<PollAnswer> | The possible answers, vote using messages.sendVote. |
| close_period | flags.4?int | Amount of time in seconds the poll will be active after creation, 5-600. Can't be used together with close_date. |
| close_date | flags.5?int | Point in time (Unix timestamp) when the poll will be automatically closed. Must be at least 5 and no more than 600 seconds in the future; can't be used together with close_period. |


## Type
Poll

## Related pages
