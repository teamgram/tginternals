# account.updatePasswordSettings
Set a new 2FA password

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.updatePasswordSettings#a59b102f password:InputCheckPasswordSRP new_settings:account.PasswordInputSettings = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| password | InputCheckPasswordSRP | The old password (see SRP) |
| new_settings | account.PasswordInputSettings | The new password (see SRP) |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | EMAIL_INVALID | The specified email is invalid. |
| 400 | EMAIL_UNCONFIRMED | Email unconfirmed. |
| 400 | EMAIL_UNCONFIRMED_%d | The provided email isn't confirmed, %d is the length of the verification code that was just sent to the email: use account.verifyEmail to enter the received verification code and enable the recovery email. |
| 400 | NEW_SALT_INVALID | The new salt is invalid. |
| 400 | NEW_SETTINGS_EMPTY | No password is set on the current account, and no new password was specified in new_settings. |
| 400 | NEW_SETTINGS_INVALID | The new password settings are invalid. |
| 400 | PASSWORD_HASH_INVALID | The provided password hash is invalid. |
| 400 | SRP_ID_INVALID | Invalid SRP ID provided. |
| 400 | SRP_PASSWORD_CHANGED | Password has changed. |

