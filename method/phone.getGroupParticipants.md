# phone.getGroupParticipants
Get group call participants

```
phone.groupParticipants#f47751b6 count:int participants:Vector<GroupCallParticipant> next_offset:string chats:Vector<Chat> users:Vector<User> version:int = phone.GroupParticipants;
---functions---
phone.getGroupParticipants#c558d8ab call:InputGroupCall ids:Vector<InputPeer> sources:Vector<int> offset:string limit:int = phone.GroupParticipants;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| call | InputGroupCall | Group call |
| ids | Vector<InputPeer> | If specified, will fetch group participant info about the specified peers |
| sources | Vector<int> | If specified, will fetch group participant info about the specified WebRTC source IDs |
| offset | string | Offset for results, taken from the next_offset field of phone.groupParticipants, initially an empty string. Note: if no more results are available, the method call will return an empty next_offset; thus, avoid providing the next_offset returned in phone.groupParticipants if it is empty, to avoid an infinite loop. |
| limit | int | Maximum number of results to return, see pagination |


## Result
phone.GroupParticipants

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

