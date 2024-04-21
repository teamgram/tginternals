# messages.saveDefaultSendAs
Change the default peer that should be used when sending messages, reactions, poll votes to a specific group

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.saveDefaultSendAs#ccfddf96 peer:InputPeer send_as:InputPeer = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Group |
| send_as | InputPeer | The default peer that should be used when sending messages to the group |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | SEND_AS_PEER_INVALID | You can't send messages as the specified peer. |

