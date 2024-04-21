# pollResults
Results of poll

```
pollResults#7adf2420 flags:# min:flags.0?true results:flags.1?Vector<PollAnswerVoters> total_voters:flags.2?int recent_voters:flags.3?Vector<Peer> solution:flags.4?string solution_entities:flags.4?Vector<MessageEntity> = PollResults;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| min | flags.0?true | Similar to min objects, used for poll constructors that are the same for all users so they don't have the option chosen by the current user (you can use messages.getPollResults to get the full poll results). |
| results | flags.1?Vector<PollAnswerVoters> | Poll results |
| total_voters | flags.2?int | Total number of people that voted in the poll |
| recent_voters | flags.3?Vector<Peer> | IDs of the last users that recently voted in the poll |
| solution | flags.4?string | Explanation of quiz solution |
| solution_entities | flags.4?Vector<MessageEntity> | Message entities for styled text in quiz solution |


## Type
PollResults

## Related pages
