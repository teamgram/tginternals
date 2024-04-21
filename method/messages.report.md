# messages.report
Report a message in a chat for violation of telegram's Terms of Service

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.report#8953ab4e peer:InputPeer id:Vector<int> reason:ReportReason message:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer |
| id | Vector<int> | IDs of messages to report |
| reason | ReportReason | Why are these messages being reported |
| message | string | Comment for report moderation |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

