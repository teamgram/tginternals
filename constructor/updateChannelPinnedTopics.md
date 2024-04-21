# updateChannelPinnedTopics
The pinned topics of a forum have changed.

```
updateChannelPinnedTopics#fe198602 flags:# channel_id:long order:flags.0?Vector<int> = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| channel_id | long | Forum ID. |
| order | flags.0?Vector<int> | Ordered list containing the IDs of all pinned topics. |


## Type
Update

## Related pages
