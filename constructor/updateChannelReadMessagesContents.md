# updateChannelReadMessagesContents
The specified channel/supergroup messages were read

```
updateChannelReadMessagesContents#ea29055d flags:# channel_id:long top_msg_id:flags.0?int messages:Vector<int> = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| channel_id | long | Channel/supergroup ID |
| top_msg_id | flags.0?int | Forum topic ID. |
| messages | Vector<int> | IDs of messages that were read |


## Type
Update

## Related pages
