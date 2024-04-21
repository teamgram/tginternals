# inputMediaPoll
A poll

```
inputMediaPoll#f94e5f1 flags:# poll:Poll correct_answers:flags.0?Vector<bytes> solution:flags.1?string solution_entities:flags.1?Vector<MessageEntity> = InputMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| poll | Poll | The poll to send |
| correct_answers | flags.0?Vector<bytes> | Correct answer IDs (for quiz polls) |
| solution | flags.1?string | Explanation of quiz solution |
| solution_entities | flags.1?Vector<MessageEntity> | Message entities for styled text |


## Type
InputMedia

## Related pages
