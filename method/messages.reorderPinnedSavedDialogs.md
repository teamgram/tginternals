# messages.reorderPinnedSavedDialogs
Reorder pinned saved message dialogs ».

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.reorderPinnedSavedDialogs#8b716587 flags:# force:flags.0?true order:Vector<InputDialogPeer> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| force | flags.0?true | If set, dialogs pinned server-side but not present in the order field will be unpinned. |
| order | Vector<InputDialogPeer> | New dialog order |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

