# phone.groupParticipants
Info about the participants of a group call or livestream

```
phone.groupParticipants#f47751b6 count:int participants:Vector<GroupCallParticipant> next_offset:string chats:Vector<Chat> users:Vector<User> version:int = phone.GroupParticipants;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| count | int | Number of participants |
| participants | Vector<GroupCallParticipant> | List of participants |
| next_offset | string | If not empty, the specified list of participants is partial, and more participants can be fetched specifying this parameter as offset in phone.getGroupParticipants. |
| chats | Vector<Chat> | Mentioned chats |
| users | Vector<User> | Mentioned users |
| version | int | Version info |


## Type
phone.GroupParticipants

## Related pages
