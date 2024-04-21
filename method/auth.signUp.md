# auth.signUp
Registers a validated phone number in the system.

```
auth.authorization#2ea2c0d4 flags:# setup_password_required:flags.1?true otherwise_relogin_days:flags.1?int tmp_sessions:flags.0?int future_auth_token:flags.2?bytes user:User = auth.Authorization;
auth.authorizationSignUpRequired#44747e9a flags:# terms_of_service:flags.0?help.TermsOfService = auth.Authorization;
---functions---
auth.signUp#80eee427 phone_number:string phone_code_hash:string first_name:string last_name:string = auth.Authorization;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| phone_number | string | Phone number in the international format |
| phone_code_hash | string | SMS-message ID |
| first_name | string | New user first name |
| last_name | string | New user last name |


## Result
auth.Authorization

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | FIRSTNAME_INVALID | The first name is invalid. |
| 400 | LASTNAME_INVALID | The last name is invalid. |
| 400 | PHONE_CODE_EMPTY | phone_code is missing. |
| 400 | PHONE_CODE_EXPIRED | The phone code you provided has expired. |
| 400 | PHONE_CODE_INVALID | The provided phone code is invalid. |
| 400 | PHONE_NUMBER_FLOOD | You asked for the code too many times. |
| 406 | PHONE_NUMBER_INVALID | The phone number is invalid. |
| 400 | PHONE_NUMBER_OCCUPIED | The phone number is already in use. |

