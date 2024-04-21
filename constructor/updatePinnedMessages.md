# updatePinnedMessages
Some messages were pinned in a chat

```
updatePinnedMessages#ed85eab5 flags:# pinned:flags.0?true peer:Peer messages:Vector<int> pts:int pts_count:int = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| pinned | flags.0?true | Whether the messages were pinned or unpinned |
| peer | Peer | Peer |
| messages | Vector<int> | Message IDs |
| pts | int | Event count after generation |
| pts_count | int | Number of events that were generated |


## Type
Update

## Related pages
