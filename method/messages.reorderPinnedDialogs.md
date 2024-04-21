# messages.reorderPinnedDialogs
Reorder pinned dialogs

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.reorderPinnedDialogs#3b1adf37 flags:# force:flags.0?true folder_id:int order:Vector<InputDialogPeer> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| force | flags.0?true | If set, dialogs pinned server-side but not present in the order field will be unpinned. |
| folder_id | int | Peer folder ID, for more info click here |
| order | Vector<InputDialogPeer> | New dialog order |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

