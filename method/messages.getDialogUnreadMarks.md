# messages.getDialogUnreadMarks
Get dialogs manually marked as unread

```
---functions---
messages.getDialogUnreadMarks#21202222 flags:# parent_peer:flags.0?InputPeer = Vector<DialogPeer>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| parent_peer | flags.0?InputPeer | Can be equal to the ID of a monoforum, to fetch monoforum topics manually marked as unread. |


## Result
Vector<DialogPeer>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

