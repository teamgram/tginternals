# phone.checkGroupCall
Check whether the group call Server Forwarding Unit is currently receiving the streams with the specified WebRTC source IDs.
Returns an intersection of the source IDs specified in sources, and the source IDs currently being forwarded by the SFU.

```
---functions---
phone.checkGroupCall#b59cf977 call:InputGroupCall sources:Vector<int> = Vector<int>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| call | InputGroupCall | Group call |
| sources | Vector<int> | Source IDs |


## Result
Vector<int>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | GROUPCALL_JOIN_MISSING | You haven't joined this group call. |

