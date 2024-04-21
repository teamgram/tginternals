# auth.importLoginToken
Login using a redirected login token, generated in case of DC mismatch during QR code login.

```
auth.loginToken#629f1980 expires:int token:bytes = auth.LoginToken;
auth.loginTokenMigrateTo#68e9916 dc_id:int token:bytes = auth.LoginToken;
auth.loginTokenSuccess#390d5c5e authorization:auth.Authorization = auth.LoginToken;
---functions---
auth.importLoginToken#95ac5ce4 token:bytes = auth.LoginToken;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| token | bytes | Login token |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | AUTH_TOKEN_ALREADY_ACCEPTED | The specified auth token was already accepted. |
| 400 | AUTH_TOKEN_EXPIRED | The authorization token has expired. |
| 400 | AUTH_TOKEN_INVALID | The specified auth token is invalid. |
| 400 | AUTH_TOKEN_INVALIDX | The specified auth token is invalid. |

