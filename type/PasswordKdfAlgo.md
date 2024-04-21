# PasswordKdfAlgo
Key derivation function to use when generating the password hash for SRP two-factor authorization

```
passwordKdfAlgoUnknown#d45ab096 = PasswordKdfAlgo;
passwordKdfAlgoSHA256SHA256PBKDF2HMACSHA512iter100000SHA256ModPow#3a912d4a salt1:bytes salt2:bytes g:int p:bytes = PasswordKdfAlgo;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| passwordKdfAlgoUnknown | Unknown KDF (most likely, the client is outdated and does not support the specified KDF algorithm) |
| passwordKdfAlgoSHA256SHA256PBKDF2HMACSHA512iter100000SHA256ModPow | This key derivation algorithm defines that SRP 2FA login must be used |


## Methods
| Method | Description |
| ---- | ----------- |


