# phone.groupCall
Contains info about a group call, and partial info about its participants.

```
phone.groupCall#9e727aad call:GroupCall participants:Vector<GroupCallParticipant> participants_next_offset:string chats:Vector<Chat> users:Vector<User> = phone.GroupCall;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| call | GroupCall | Info about the group call |
| participants | Vector<GroupCallParticipant> | A partial list of participants. |
| participants_next_offset | string | Next offset to use when fetching the remaining participants using phone.getGroupParticipants |
| chats | Vector<Chat> | Chats mentioned in the participants vector |
| users | Vector<User> | Users mentioned in the participants vector |


## Type
phone.GroupCall

## Related pages
