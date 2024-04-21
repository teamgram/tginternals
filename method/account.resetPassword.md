# account.resetPassword
Initiate a 2FA password reset: can only be used if the user is already logged-in, see here for more info »

```
account.resetPasswordFailedWait#e3779861 retry_date:int = account.ResetPasswordResult;
account.resetPasswordRequestedWait#e9effc7d until_date:int = account.ResetPasswordResult;
account.resetPasswordOk#e926d63e = account.ResetPasswordResult;
---functions---
account.resetPassword#9308ce1b = account.ResetPasswordResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| 400 | PASSWORD_EMPTY | The provided password is empty. |


## Result
This constructor does not require any parameters.

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

