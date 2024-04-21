# auth.requestPasswordRecovery
Request recovery code of a 2FA password, only for accounts with a recovery email configured.

```
auth.passwordRecovery#137948a5 email_pattern:string = auth.PasswordRecovery;
---functions---
auth.requestPasswordRecovery#d897bc66 = auth.PasswordRecovery;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| 400 | PASSWORD_EMPTY | The provided password is empty. |
| 400 | PASSWORD_RECOVERY_NA | No email was set, can't recover password via email. |


## Result
This constructor does not require any parameters.

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

