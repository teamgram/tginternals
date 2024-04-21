# updates.channelDifference
The new updates

```
updates.channelDifference#2064674e flags:# final:flags.0?true pts:int timeout:flags.1?int new_messages:Vector<Message> other_updates:Vector<Update> chats:Vector<Chat> users:Vector<User> = updates.ChannelDifference;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| final | flags.0?true | Whether there are more updates to be fetched using getDifference, starting from the provided pts |
| pts | int | The PTS from which to start getting updates the next time |
| timeout | flags.1?int | Clients are supposed to refetch the channel difference after timeout seconds have elapsed |
| new_messages | Vector<Message> | New messages |
| other_updates | Vector<Update> | Other updates |
| chats | Vector<Chat> | Chats |
| users | Vector<User> | Users |


## Type
updates.ChannelDifference

## Related pages
