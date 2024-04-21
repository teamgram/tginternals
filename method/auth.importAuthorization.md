# auth.importAuthorization
Logs in a user using a key transmitted from his native data-center.

```
auth.authorization#2ea2c0d4 flags:# setup_password_required:flags.1?true otherwise_relogin_days:flags.1?int tmp_sessions:flags.0?int future_auth_token:flags.2?bytes user:User = auth.Authorization;
auth.authorizationSignUpRequired#44747e9a flags:# terms_of_service:flags.0?help.TermsOfService = auth.Authorization;
---functions---
auth.importAuthorization#a57a7dad id:long bytes:bytes = auth.Authorization;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | long | User ID |
| bytes | bytes | Authorization key |


## Result
auth.Authorization

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | AUTH_BYTES_INVALID | The provided authorization is invalid. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

