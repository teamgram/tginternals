# updateReadHistoryInbox
Incoming messages were read

```
updateReadHistoryInbox#9c974fdf flags:# folder_id:flags.0?int peer:Peer max_id:int still_unread_count:int pts:int pts_count:int = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| folder_id | flags.0?int | Peer folder ID, for more info click here |
| peer | Peer | Peer |
| max_id | int | Maximum ID of messages read |
| still_unread_count | int | Number of messages that are still unread |
| pts | int | Event count after generation |
| pts_count | int | Number of events that were generated |


## Type
Update

## Related pages
