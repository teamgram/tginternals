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
| 400 | ENCRYPTED_MESSAGE_INVALID | Encrypted message invalid. |
| 400 | TEMP_AUTH_KEY_ALREADY_BOUND | The passed temporary key is already bound to another perm_auth_key_id. |
| 400 | TEMP_AUTH_KEY_EMPTY | No temporary auth key provided. |

