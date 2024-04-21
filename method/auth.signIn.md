# auth.signIn
Signs in a user with a validated phone number.

```
auth.authorization#2ea2c0d4 flags:# setup_password_required:flags.1?true otherwise_relogin_days:flags.1?int tmp_sessions:flags.0?int future_auth_token:flags.2?bytes user:User = auth.Authorization;
auth.authorizationSignUpRequired#44747e9a flags:# terms_of_service:flags.0?help.TermsOfService = auth.Authorization;
---functions---
auth.signIn#8d52a951 flags:# phone_number:string phone_code_hash:string phone_code:flags.0?string email_verification:flags.1?EmailVerification = auth.Authorization;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| phone_number | string | Phone number in the international format |
| phone_code_hash | string | SMS-message ID, obtained from auth.sendCode |
| phone_code | flags.0?string | Valid numerical code from the SMS-message |
| email_verification | flags.1?EmailVerification | Email verification code or token |


## Result
auth.Authorization

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 500 | AUTH_RESTART | Restart the authorization process. |
| 400 | PHONE_CODE_EMPTY | phone_code is missing. |
| 400 | PHONE_CODE_EXPIRED | The phone code you provided has expired. |
| 400 | PHONE_CODE_INVALID | The provided phone code is invalid. |
| 406 | PHONE_NUMBER_INVALID | The phone number is invalid. |
| 400 | PHONE_NUMBER_UNOCCUPIED | The phone number is not yet being used. |
| 500 | SIGN_IN_FAILED | Failure while signing in. |

