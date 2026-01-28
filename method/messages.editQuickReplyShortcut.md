# messages.editQuickReplyShortcut
Rename a quick reply shortcut.
This will emit an updateQuickReplies update to other logged-in sessions.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.editQuickReplyShortcut#5c003cef shortcut_id:int shortcut:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| shortcut_id | int | Shortcut ID. |
| shortcut | string | New shortcut name. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | PREMIUM_ACCOUNT_REQUIRED | A premium account is required to execute this action. |
| 400 | SHORTCUT_INVALID | The specified shortcut is invalid. |

