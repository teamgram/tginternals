# auth.exportLoginToken
Generate a login token, for login via QR code.
The generated login token should be encoded using base64url, then shown as a tg://login?token=base64encodedtoken deep link » in the QR code.

```
auth.loginToken#629f1980 expires:int token:bytes = auth.LoginToken;
auth.loginTokenMigrateTo#68e9916 dc_id:int token:bytes = auth.LoginToken;
auth.loginTokenSuccess#390d5c5e authorization:auth.Authorization = auth.LoginToken;
---functions---
auth.exportLoginToken#b7e085fe api_id:int api_hash:string except_ids:Vector<long> = auth.LoginToken;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| api_id | int | Application identifier (see. App configuration) |
| api_hash | string | Application identifier hash (see. App configuration) |
| except_ids | Vector<long> | List of already logged-in user IDs, to prevent logging in twice with the same user |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | API_ID_INVALID | API ID invalid. |
| 400 | API_ID_PUBLISHED_FLOOD | This API id was published somewhere, you can't use it now. |

