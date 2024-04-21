# updateReadChannelDiscussionInbox
Incoming comments in a discussion thread were marked as read

```
updateReadChannelDiscussionInbox#d6b19546 flags:# channel_id:long top_msg_id:int read_max_id:int broadcast_id:flags.0?long broadcast_post:flags.0?int = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| channel_id | long | Discussion group ID |
| top_msg_id | int | ID of the group message that started the thread (message in linked discussion group) |
| read_max_id | int | Message ID of latest read incoming message for this thread |
| broadcast_id | flags.0?long | If set, contains the ID of the channel that contains the post that started the comment thread in the discussion group (channel_id) |
| broadcast_post | flags.0?int | If set, contains the ID of the channel post that started the comment thread |


## Type
Update

## Related pages
