# account.reportProfilePhoto
Report a profile photo of a dialog

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.reportProfilePhoto#fa8cc6f5 peer:InputPeer photo_id:InputPhoto reason:ReportReason message:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The dialog |
| photo_id | InputPhoto | Dialog photo ID |
| reason | ReportReason | Report reason |
| message | string | Comment for report moderation |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

