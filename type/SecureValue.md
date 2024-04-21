# SecureValue
Secure Telegram Passport value

```
secureValue#187fa0ca flags:# type:SecureValueType data:flags.0?SecureData front_side:flags.1?SecureFile reverse_side:flags.2?SecureFile selfie:flags.3?SecureFile translation:flags.6?Vector<SecureFile> files:flags.4?Vector<SecureFile> plain_data:flags.5?SecurePlainData hash:bytes = SecureValue;

---functions---

account.saveSecureValue#899fe31d value:InputSecureValue secure_secret_id:long = SecureValue;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| secureValue | Secure value |


## Methods
| Method | Description |
| ---- | ----------- |
| account.saveSecureValue | Securely save Telegram Passport document, for more info see the passport docs » |


