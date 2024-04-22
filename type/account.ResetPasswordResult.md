# account.ResetPasswordResult
Result of an account.resetPassword request.

```
account.resetPasswordFailedWait#e3779861 retry_date:int = account.ResetPasswordResult;
account.resetPasswordRequestedWait#e9effc7d until_date:int = account.ResetPasswordResult;
account.resetPasswordOk#e926d63e = account.ResetPasswordResult;

---functions---

account.resetPassword#9308ce1b = account.ResetPasswordResult;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| account.resetPasswordFailedWait | You recently requested a password reset that was canceled, please wait until the specified date before requesting another reset. |
| account.resetPasswordRequestedWait | You successfully requested a password reset, please wait until the specified date before finalizing the reset. |
| account.resetPasswordOk | The 2FA password was reset successfully. |


## Methods
| Method | Description |
| ---- | ----------- |
| account.resetPassword | Initiate a 2FA password reset: can only be used if the user is already logged-in, see here for more info » |


