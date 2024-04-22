# phone.GroupParticipants
Info about the participants of a group call or livestream

```
phone.groupParticipants#f47751b6 count:int participants:Vector<GroupCallParticipant> next_offset:string chats:Vector<Chat> users:Vector<User> version:int = phone.GroupParticipants;

---functions---

phone.getGroupParticipants#c558d8ab call:InputGroupCall ids:Vector<InputPeer> sources:Vector<int> offset:string limit:int = phone.GroupParticipants;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| phone.groupParticipants | Info about the participants of a group call or livestream |


## Methods
| Method | Description |
| ---- | ----------- |
| phone.getGroupParticipants | Get group call participants |


