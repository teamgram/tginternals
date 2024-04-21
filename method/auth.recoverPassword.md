# auth.recoverPassword
Reset the 2FA password using the recovery code sent using auth.requestPasswordRecovery.

```
auth.authorization#2ea2c0d4 flags:# setup_password_required:flags.1?true otherwise_relogin_days:flags.1?int tmp_sessions:flags.0?int future_auth_token:flags.2?bytes user:User = auth.Authorization;
auth.authorizationSignUpRequired#44747e9a flags:# terms_of_service:flags.0?help.TermsOfService = auth.Authorization;
---functions---
auth.recoverPassword#37096c70 flags:# code:string new_settings:flags.0?account.PasswordInputSettings = auth.Authorization;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| code | string | Code received via email |
| new_settings | flags.0?account.PasswordInputSettings | New password |


## Result
auth.Authorization

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CODE_EMPTY | The provided code is empty. |
| 400 | NEW_SETTINGS_INVALID | The new password settings are invalid. |

