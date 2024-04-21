# updateReadChannelDiscussionOutbox
Outgoing comments in a discussion thread were marked as read

```
updateReadChannelDiscussionOutbox#695c9e7c channel_id:long top_msg_id:int read_max_id:int = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel_id | long | Supergroup ID |
| top_msg_id | int | ID of the group message that started the thread |
| read_max_id | int | Message ID of latest read outgoing message for this thread |


## Type
Update

## Related pages
