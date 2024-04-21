# account.resetAuthorization
Log out an active authorized session by its hash

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.resetAuthorization#df77f3bc hash:long = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| hash | long | Session hash |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 406 | FRESH_RESET_AUTHORISATION_FORBIDDEN | You can't logout other sessions if less than 24 hours have passed since you logged on the current session. |
| 400 | HASH_INVALID | The provided hash is invalid. |

