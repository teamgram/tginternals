# messages.setDefaultHistoryTTL
Changes the default value of the Time-To-Live setting, applied to all new chats.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.setDefaultHistoryTTL#9eb51445 period:int = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| period | int | The new default Time-To-Live of all messages sent in new chats. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | TTL_PERIOD_INVALID | The specified TTL period is invalid. |

