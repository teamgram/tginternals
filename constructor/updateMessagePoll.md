# updateMessagePoll
The results of a poll have changed

```
updateMessagePoll#aca1657b flags:# poll_id:long poll:flags.0?Poll results:PollResults = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| poll_id | long | Poll ID |
| poll | flags.0?Poll | If the server knows the client hasn't cached this poll yet, the poll itself |
| results | PollResults | New poll results |


## Type
Update

## Related pages
