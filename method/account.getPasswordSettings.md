# account.getPasswordSettings
Get private info associated to the password info (recovery email, telegram passport info & so on)

```
account.passwordSettings#9a5c33e5 flags:# email:flags.0?string secure_settings:flags.1?SecureSecretSettings = account.PasswordSettings;
---functions---
account.getPasswordSettings#9cd4eaf9 password:InputCheckPasswordSRP = account.PasswordSettings;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| password | InputCheckPasswordSRP | The password (see SRP) |


## Result
account.PasswordSettings

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PASSWORD_HASH_INVALID | The provided password hash is invalid. |

