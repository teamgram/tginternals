# passwordKdfAlgoSHA256SHA256PBKDF2HMACSHA512iter100000SHA256ModPow
This key derivation algorithm defines that SRP 2FA login must be used

```
passwordKdfAlgoSHA256SHA256PBKDF2HMACSHA512iter100000SHA256ModPow#3a912d4a salt1:bytes salt2:bytes g:int p:bytes = PasswordKdfAlgo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| salt1 | bytes | One of two salts used by the derivation function (see SRP 2FA login) |
| salt2 | bytes | One of two salts used by the derivation function (see SRP 2FA login) |
| g | int | Base (see SRP 2FA login) |
| p | bytes | 2048-bit modulus (see SRP 2FA login) |


## Type
PasswordKdfAlgo

## Related pages
