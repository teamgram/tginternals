# auth.checkRecoveryPassword
Check if the 2FA recovery code sent using auth.requestPasswordRecovery is valid, before passing it to auth.recoverPassword.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
auth.checkRecoveryPassword#d36bf79 code:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| code | string | Code received via email |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PASSWORD_RECOVERY_EXPIRED | The recovery code has expired. |

