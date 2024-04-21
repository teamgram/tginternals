# messages.reportReaction
Report a message reaction

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.reportReaction#3f64c076 peer:InputPeer id:int reaction_peer:InputPeer = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer where the message was sent |
| id | int | Message ID |
| reaction_peer | InputPeer | Peer that sent the reaction |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

