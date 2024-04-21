# updates.channelDifferenceTooLong
The provided pts + limit < remote pts. Simply, there are too many updates to be fetched (more than limit), the client has to resolve the update gap in one of the following ways (assuming the existence of a persistent database to locally store messages):

```
updates.channelDifferenceTooLong#a4bcc6fe flags:# final:flags.0?true timeout:flags.1?int dialog:Dialog messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = updates.ChannelDifference;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| final | flags.0?true | Whether there are more updates that must be fetched (always false) |
| timeout | flags.1?int | Clients are supposed to refetch the channel difference after timeout seconds have elapsed |
| dialog | Dialog | Dialog containing the latest PTS that can be used to reset the channel state |
| messages | Vector<Message> | The latest messages |
| chats | Vector<Chat> | Chats from messages |
| users | Vector<User> | Users from messages |


## Type


## Related pages
