# messages.toggleSavedDialogPin
Pin or unpin a saved message dialog ».

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.toggleSavedDialogPin#ac81bbde flags:# pinned:flags.0?true peer:InputDialogPeer = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| pinned | flags.0?true | Whether to pin or unpin the dialog |
| peer | InputDialogPeer | The dialog to pin |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

