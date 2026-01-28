# account.updateBusinessWorkHours
Specify a set of Telegram Business opening hours.
This info will be contained in userFull.business_work_hours.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.updateBusinessWorkHours#4b00e066 flags:# business_work_hours:flags.0?BusinessWorkHours = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| business_work_hours | flags.0?BusinessWorkHours | Opening hours (optional, if not set removes all opening hours). |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BUSINESS_WORK_HOURS_EMPTY | No work hours were specified. |
| 400 | BUSINESS_WORK_HOURS_PERIOD_INVALID | The specified work hours are invalid, see here » for the exact requirements. |
| 400 | TIMEZONE_INVALID | The specified timezone does not exist. |

