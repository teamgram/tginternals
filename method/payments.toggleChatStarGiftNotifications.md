# payments.toggleChatStarGiftNotifications
Enables or disables the reception of notifications every time a gift » is received by the specified channel, can only be invoked by admins with post_messages admin rights.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
payments.toggleChatStarGiftNotifications#60eaefa1 flags:# enabled:flags.0?true peer:InputPeer = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| enabled | flags.0?true | Whether to enable or disable reception of notifications in the form of messageActionStarGiftUnique and messageActionStarGift service messages from the channel. |
| peer | InputPeer | The channel for which to receive or not receive notifications. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

