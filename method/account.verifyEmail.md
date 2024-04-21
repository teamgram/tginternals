# account.verifyEmail
Verify an email address.

```
account.emailVerified#2b96cd1b email:string = account.EmailVerified;
account.emailVerifiedLogin#e1bb0d61 email:string sent_code:auth.SentCode = account.EmailVerified;
---functions---
account.verifyEmail#32da4cf purpose:EmailVerifyPurpose verification:EmailVerification = account.EmailVerified;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| purpose | EmailVerifyPurpose | Verification purpose |
| verification | EmailVerification | Email verification code or token |


## Result
account.EmailVerified

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | EMAIL_INVALID | The specified email is invalid. |
| 400 | EMAIL_VERIFY_EXPIRED | The verification email has expired. |

