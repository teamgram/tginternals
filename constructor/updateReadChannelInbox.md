# updateReadChannelInbox
Incoming messages in a channel/supergroup were read

```
updateReadChannelInbox#922e6e10 flags:# folder_id:flags.0?int channel_id:long max_id:int still_unread_count:int pts:int = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| folder_id | flags.0?int | Peer folder ID, for more info click here |
| channel_id | long | Channel/supergroup ID |
| max_id | int | Position up to which all incoming messages are read. |
| still_unread_count | int | Count of messages weren't read yet |
| pts | int | Event count after generation |


## Type
Update

## Related pages
