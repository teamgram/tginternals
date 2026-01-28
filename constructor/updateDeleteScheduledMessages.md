# updateDeleteScheduledMessages
Some scheduled messages were deleted (or sent) from the schedule queue of a chat

```
updateDeleteScheduledMessages#f2a71983 flags:# peer:Peer messages:Vector<int> sent_messages:flags.0?Vector<int> = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | Peer | Peer |
| messages | Vector<int> | Deleted scheduled messages |
| sent_messages | flags.0?Vector<int> | If set, this update indicates that some scheduled messages were sent (not simply deleted from the schedule queue).  In this case, the messages field will contain the scheduled message IDs for the sent messages (initially returned in updateNewScheduledMessage), and sent_messages will contain the real message IDs for the sent messages. |


## Type
Update

## Related pages
