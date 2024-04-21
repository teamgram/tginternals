# auth.checkPassword
Try logging to an account protected by a 2FA password.

```
auth.authorization#2ea2c0d4 flags:# setup_password_required:flags.1?true otherwise_relogin_days:flags.1?int tmp_sessions:flags.0?int future_auth_token:flags.2?bytes user:User = auth.Authorization;
auth.authorizationSignUpRequired#44747e9a flags:# terms_of_service:flags.0?help.TermsOfService = auth.Authorization;
---functions---
auth.checkPassword#d18b4d16 password:InputCheckPasswordSRP = auth.Authorization;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| password | InputCheckPasswordSRP | The account's password (see SRP) |


## Result
auth.Authorization

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PASSWORD_HASH_INVALID | The provided password hash is invalid. |
| 400 | SRP_ID_INVALID | Invalid SRP ID provided. |
| 400 | SRP_PASSWORD_CHANGED | Password has changed. |

