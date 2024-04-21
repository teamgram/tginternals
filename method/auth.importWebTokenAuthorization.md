# auth.importWebTokenAuthorization
Login by importing an authorization token

```
auth.authorization#2ea2c0d4 flags:# setup_password_required:flags.1?true otherwise_relogin_days:flags.1?int tmp_sessions:flags.0?int future_auth_token:flags.2?bytes user:User = auth.Authorization;
auth.authorizationSignUpRequired#44747e9a flags:# terms_of_service:flags.0?help.TermsOfService = auth.Authorization;
---functions---
auth.importWebTokenAuthorization#2db873a9 api_id:int api_hash:string web_auth_token:string = auth.Authorization;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| api_id | int | API ID |
| api_hash | string | API hash |
| web_auth_token | string | The authorization token |


## Result
auth.Authorization

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | API_ID_INVALID | API ID invalid. |

