# updates.channelDifferenceEmpty
There are no new updates

```
updates.channelDifferenceEmpty#3e11affb flags:# final:flags.0?true pts:int timeout:flags.1?int = updates.ChannelDifference;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| final | flags.0?true | Whether there are more updates that must be fetched (always false) |
| pts | int | The latest PTS |
| timeout | flags.1?int | Clients are supposed to refetch the channel difference after timeout seconds have elapsed |


## Type
updates.ChannelDifference

## Related pages
