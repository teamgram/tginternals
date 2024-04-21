# updateChannelUserTyping
A user is typing in a supergroup, channel or message thread

```
updateChannelUserTyping#8c88c923 flags:# channel_id:long top_msg_id:flags.0?int from_id:Peer action:SendMessageAction = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| channel_id | long | Channel ID |
| top_msg_id | flags.0?int | Thread ID |
| from_id | Peer | The peer that is typing |
| action | SendMessageAction | Whether the user is typing, sending a media or doing something else |


## Type
Update

## Related pages
