# account.reportPeer
Report a peer for violation of telegram's Terms of Service

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.reportPeer#c5ba3d86 peer:InputPeer reason:ReportReason message:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The peer to report |
| reason | ReportReason | The reason why this peer is being reported |
| message | string | Comment for report moderation |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

