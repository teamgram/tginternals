# account.getTmpPassword
Get temporary payment password

```
account.tmpPassword#db64fd34 tmp_password:bytes valid_until:int = account.TmpPassword;
---functions---
account.getTmpPassword#449e0b51 password:InputCheckPasswordSRP period:int = account.TmpPassword;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| password | InputCheckPasswordSRP | SRP password parameters |
| period | int | Time during which the temporary password will be valid, in seconds; should be between 60 and 86400 |


## Result
account.TmpPassword

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PASSWORD_HASH_INVALID | The provided password hash is invalid. |
| 400 | TMP_PASSWORD_DISABLED | The temporary password is disabled. |

