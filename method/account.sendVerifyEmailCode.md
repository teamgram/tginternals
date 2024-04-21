# account.sendVerifyEmailCode
Send an email verification code.

```
account.sentEmailCode#811f854f email_pattern:string length:int = account.SentEmailCode;
---functions---
account.sendVerifyEmailCode#98e037bb purpose:EmailVerifyPurpose email:string = account.SentEmailCode;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| purpose | EmailVerifyPurpose | Verification purpose. |
| email | string | The email where to send the code. |


## Result
account.SentEmailCode

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | EMAIL_INVALID | The specified email is invalid. |
| 400 | EMAIL_NOT_SETUP | In order to change the login email with emailVerifyPurposeLoginChange, an existing login email must already be set using emailVerifyPurposeLoginSetup. |
| 400 | PHONE_HASH_EXPIRED | An invalid or expired phone_code_hash was provided. |
| 400 | PHONE_NUMBER_INVALID | The phone number is invalid. |

