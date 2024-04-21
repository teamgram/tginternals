# account.saveSecureValue
Securely save Telegram Passport document, for more info see the passport docs »

```
secureValue#187fa0ca flags:# type:SecureValueType data:flags.0?SecureData front_side:flags.1?SecureFile reverse_side:flags.2?SecureFile selfie:flags.3?SecureFile translation:flags.6?Vector<SecureFile> files:flags.4?Vector<SecureFile> plain_data:flags.5?SecurePlainData hash:bytes = SecureValue;
---functions---
account.saveSecureValue#899fe31d value:InputSecureValue secure_secret_id:long = SecureValue;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| value | InputSecureValue | Secure value, for more info see the passport docs » |
| secure_secret_id | long | Passport secret hash, for more info see the passport docs » |


## Result
SecureValue

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PASSWORD_REQUIRED | A 2FA password must be configured to use Telegram Passport. |

