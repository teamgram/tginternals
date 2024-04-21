# updatePinnedChannelMessages
Messages were pinned/unpinned in a channel/supergroup

```
updatePinnedChannelMessages#5bb98608 flags:# pinned:flags.0?true channel_id:long messages:Vector<int> pts:int pts_count:int = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| pinned | flags.0?true | Whether the messages were pinned or unpinned |
| channel_id | long | Channel ID |
| messages | Vector<int> | Messages |
| pts | int | Event count after generation |
| pts_count | int | Number of events that were generated |


## Type
Update

## Related pages
