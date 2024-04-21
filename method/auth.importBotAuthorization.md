# auth.importBotAuthorization
Login as a bot

```
auth.authorization#2ea2c0d4 flags:# setup_password_required:flags.1?true otherwise_relogin_days:flags.1?int tmp_sessions:flags.0?int future_auth_token:flags.2?bytes user:User = auth.Authorization;
auth.authorizationSignUpRequired#44747e9a flags:# terms_of_service:flags.0?help.TermsOfService = auth.Authorization;
---functions---
auth.importBotAuthorization#67a3ff2c flags:int api_id:int api_hash:string bot_auth_token:string = auth.Authorization;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | int | Reserved for future use |
| api_id | int | Application identifier (see. App configuration) |
| api_hash | string | Application identifier hash (see. App configuration) |
| bot_auth_token | string | Bot token (see bots) |


## Result
auth.Authorization

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | ACCESS_TOKEN_EXPIRED | Access token expired. |
| 400 | ACCESS_TOKEN_INVALID | Access token invalid. |
| 400 | API_ID_INVALID | API ID invalid. |
| 400 | API_ID_PUBLISHED_FLOOD | This API id was published somewhere, you can't use it now. |

