# phone.getGroupCall
Get info about a group call

```
phone.groupCall#9e727aad call:GroupCall participants:Vector<GroupCallParticipant> participants_next_offset:string chats:Vector<Chat> users:Vector<User> = phone.GroupCall;
---functions---
phone.getGroupCall#41845db call:InputGroupCall limit:int = phone.GroupCall;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| call | InputGroupCall | The group call |
| limit | int | Maximum number of results to return, see pagination |


## Result
phone.GroupCall

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | GROUPCALL_FORBIDDEN | The group call has already ended. |
| 400 | GROUPCALL_INVALID | The specified group call is invalid. |

