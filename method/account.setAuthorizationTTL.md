# account.setAuthorizationTTL
Set time-to-live of current session

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.setAuthorizationTTL#bf899aa0 authorization_ttl_days:int = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| authorization_ttl_days | int | Time-to-live of current session in days |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 406 | FRESH_RESET_AUTHORISATION_FORBIDDEN | You can't logout other sessions if less than 24 hours have passed since you logged on the current session. |
| 400 | TTL_DAYS_INVALID | The provided TTL is invalid. |

