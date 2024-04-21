# account.setAccountTTL
Set account self-destruction period

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.setAccountTTL#2442485e ttl:AccountDaysTTL = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| ttl | AccountDaysTTL | Time to live in days |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | TTL_DAYS_INVALID | The provided TTL is invalid. |

