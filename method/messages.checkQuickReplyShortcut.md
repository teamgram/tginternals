# messages.checkQuickReplyShortcut
Before offering the user the choice to add a message to a quick reply shortcut, to make sure that none of the limits specified here » were reached.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.checkQuickReplyShortcut#f1d0fbd3 shortcut:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| shortcut | string | Shorcut name (not ID!). |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | PREMIUM_ACCOUNT_REQUIRED | A premium account is required to execute this action. |

