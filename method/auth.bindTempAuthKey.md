# auth.bindTempAuthKey
Binds a temporary authorization key temp_auth_key_id to the permanent authorization key perm_auth_key_id. Each permanent key may only be bound to one temporary key at a time, binding a new temporary key overwrites the previous one.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
auth.bindTempAuthKey#cdd42a05 perm_auth_key_id:long nonce:long expires_at:int encrypted_message:bytes = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| perm_auth_key_id | long | Permanent auth_key_id to bind to |
| nonce | long | Random long from Binding message contents |
| expires_at | int | Unix timestamp to invalidate temporary key, see Binding message contents |
| encrypted_message | bytes | See Generating encrypted_message |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| nonce | long | Random long |
| temp_auth_key_id | long | Temporary auth_key_id |
| perm_auth_key_id | long | Permanent auth_key_id to bind to |
| temp_session_id | long | Session id, which will be used to invoke auth.bindTempAuthKey method |
| expires_at | int | Unix timestamp to invalidate temporary key |

