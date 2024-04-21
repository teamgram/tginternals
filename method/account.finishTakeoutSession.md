# account.finishTakeoutSession
Terminate a takeout session, see here » for more info.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.finishTakeoutSession#1d2652ee flags:# success:flags.0?true = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| success | flags.0?true | Data exported successfully |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | TAKEOUT_REQUIRED | A takeout session needs to be initialized first, see here » for more info. |

