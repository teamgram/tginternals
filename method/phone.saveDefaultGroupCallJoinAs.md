# phone.saveDefaultGroupCallJoinAs
Set the default peer that will be used to join a group call in a specific dialog.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
phone.saveDefaultGroupCallJoinAs#575e1f8c peer:InputPeer join_as:InputPeer = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The dialog |
| join_as | InputPeer | The default peer that will be used to join group calls in this dialog, presenting yourself as a specific user/channel. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | JOIN_AS_PEER_INVALID | The specified peer cannot be used to join a group call. |

