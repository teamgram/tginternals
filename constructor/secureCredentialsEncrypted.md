# secureCredentialsEncrypted
Encrypted credentials required to decrypt telegram passport data.

```
secureCredentialsEncrypted#33f0ea47 data:bytes hash:bytes secret:bytes = SecureCredentialsEncrypted;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| data | bytes | Encrypted JSON-serialized data with unique user's payload, data hashes and secrets required for EncryptedPassportElement decryption and authentication, as described in decrypting data » |
| hash | bytes | Data hash for data authentication as described in decrypting data » |
| secret | bytes | Secret, encrypted with the bot's public RSA key, required for data decryption as described in decrypting data » |


## Type
SecureCredentialsEncrypted

## Related pages
