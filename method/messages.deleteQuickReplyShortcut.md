# messages.deleteQuickReplyShortcut
Completely delete a quick reply shortcut.
This will also emit an updateDeleteQuickReply update to other logged-in sessions (and no updateDeleteQuickReplyMessages updates, even if all the messages in the shortcuts are also deleted by this method).

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.deleteQuickReplyShortcut#3cc04740 shortcut_id:int = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| shortcut_id | int | Shortcut ID |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | SHORTCUT_INVALID | The specified shortcut is invalid. |

