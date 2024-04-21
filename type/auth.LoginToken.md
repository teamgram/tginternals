# auth.LoginToken
Login token (for QR code login)

```
auth.loginToken#629f1980 expires:int token:bytes = auth.LoginToken;
auth.loginTokenMigrateTo#68e9916 dc_id:int token:bytes = auth.LoginToken;
auth.loginTokenSuccess#390d5c5e authorization:auth.Authorization = auth.LoginToken;

---functions---

auth.exportLoginToken#b7e085fe api_id:int api_hash:string except_ids:Vector<long> = auth.LoginToken;
auth.importLoginToken#95ac5ce4 token:bytes = auth.LoginToken;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| auth.loginToken | Login token (for QR code login) |
| auth.loginTokenMigrateTo | Repeat the query to the specified DC |
| auth.loginTokenSuccess | Login via token (QR code) succeeded! |


## Methods
| Method | Description |
| ---- | ----------- |
| auth.exportLoginToken | Generate a login token, for login via QR code.  The generated login token should be encoded using base64url, then shown as a tg://login?token=base64encodedtoken deep link » in the QR code.For more info, see login via QR code. |
| auth.importLoginToken | Login using a redirected login token, generated in case of DC mismatch during QR code login.For more info, see login via QR code. |


