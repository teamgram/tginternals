# updateReadMessagesContents
Contents of messages in the common message box were read (emitted specifically for messages like voice messages or video, only once the media is watched and marked as read using messages.readMessageContents).

```
updateReadMessagesContents#f8227181 flags:# messages:Vector<int> pts:int pts_count:int date:flags.0?int = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| messages | Vector<int> | IDs of read messages |
| pts | int | Event count after generation |
| pts_count | int | Number of events that were generated |
| date | flags.0?int | When was the last message in messages marked as read. |


## Type
Update

## Related pages
