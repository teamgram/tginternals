# account.EmailVerified
Email verification status

```
account.emailVerified#2b96cd1b email:string = account.EmailVerified;
account.emailVerifiedLogin#e1bb0d61 email:string sent_code:auth.SentCode = account.EmailVerified;

---functions---

account.verifyEmail#32da4cf purpose:EmailVerifyPurpose verification:EmailVerification = account.EmailVerified;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| account.emailVerified | The email was verified correctly. |
| account.emailVerifiedLogin | The email was verified correctly, and a login code was just sent to it. |


## Methods
| Method | Description |
| ---- | ----------- |
| account.verifyEmail | Verify an email address. |


