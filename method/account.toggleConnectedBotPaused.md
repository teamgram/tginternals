# account.toggleConnectedBotPaused
Pause or unpause a specific chat, temporarily disconnecting it from all business bots ».

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.toggleConnectedBotPaused#646e1097 peer:InputPeer paused:Bool = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The chat to pause |
| paused | Bool | Whether to pause or unpause the chat |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

