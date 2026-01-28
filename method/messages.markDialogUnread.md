# messages.markDialogUnread
Manually mark dialog as unread

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.markDialogUnread#8c5006f8 flags:# unread:flags.0?true parent_peer:flags.1?InputPeer peer:InputDialogPeer = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| unread | flags.0?true | Mark as unread/read |
| parent_peer | flags.1?InputPeer | If set, must be equal to the ID of a monoforum, and will affect the monoforum topic passed in peer. |
| peer | InputDialogPeer | Dialog |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

