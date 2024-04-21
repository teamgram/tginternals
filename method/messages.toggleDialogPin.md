# messages.toggleDialogPin
Pin/unpin a dialog

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.toggleDialogPin#a731e257 flags:# pinned:flags.0?true peer:InputDialogPeer = Bool;
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
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | PEER_HISTORY_EMPTY | You can't pin an empty chat with a user. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | PINNED_DIALOGS_TOO_MUCH | Too many pinned dialogs. |

