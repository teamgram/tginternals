# pollAnswerVoters
A poll answer, and how users voted on it

```
pollAnswerVoters#3b6ddad2 flags:# chosen:flags.0?true correct:flags.1?true option:bytes voters:int = PollAnswerVoters;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| chosen | flags.0?true | Whether we have chosen this answer |
| correct | flags.1?true | For quizzes, whether the option we have chosen is correct |
| option | bytes | The param that has to be passed to messages.sendVote. |
| voters | int | How many users voted for this option |


## Type
PollAnswerVoters

## Related pages
