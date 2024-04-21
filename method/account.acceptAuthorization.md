# account.acceptAuthorization
Sends a Telegram Passport authorization form, effectively sharing data with the service

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.acceptAuthorization#f3ed4c73 bot_id:long scope:string public_key:string value_hashes:Vector<SecureValueHash> credentials:SecureCredentialsEncrypted = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| bot_id | long | Bot ID |
| scope | string | Telegram Passport element types requested by the service |
| public_key | string | Service's public key |
| value_hashes | Vector<SecureValueHash> | Types of values sent and their hashes |
| credentials | SecureCredentialsEncrypted | Encrypted values |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PUBLIC_KEY_REQUIRED | A public key is required. |

