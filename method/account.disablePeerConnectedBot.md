# account.disablePeerConnectedBot
Permanently disconnect a specific chat from all business bots » (equivalent to specifying it in recipients.exclude_users during initial configuration with account.updateConnectedBot »); to reconnect of a chat disconnected using this method the user must reconnect the entire bot by invoking account.updateConnectedBot ».

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.disablePeerConnectedBot#5e437ed9 peer:InputPeer = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The chat to disconnect |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_ALREADY_DISABLED | The connected business bot was already disabled for the specified peer. |
| 400 | BOT_NOT_CONNECTED_YET | No business bot is connected to the currently logged in user. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

