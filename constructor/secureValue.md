# secureValue
Secure value

```
secureValue#187fa0ca flags:# type:SecureValueType data:flags.0?SecureData front_side:flags.1?SecureFile reverse_side:flags.2?SecureFile selfie:flags.3?SecureFile translation:flags.6?Vector<SecureFile> files:flags.4?Vector<SecureFile> plain_data:flags.5?SecurePlainData hash:bytes = SecureValue;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| type | SecureValueType | Secure passport value type |
| data | flags.0?SecureData | Encrypted Telegram Passport element data |
| front_side | flags.1?SecureFile | Encrypted passport file with the front side of the document |
| reverse_side | flags.2?SecureFile | Encrypted passport file with the reverse side of the document |
| selfie | flags.3?SecureFile | Encrypted passport file with a selfie of the user holding the document |
| translation | flags.6?Vector<SecureFile> | Array of encrypted passport files with translated versions of the provided documents |
| files | flags.4?Vector<SecureFile> | Array of encrypted passport files with photos the of the documents |
| plain_data | flags.5?SecurePlainData | Plaintext verified passport data |
| hash | bytes | Data hash |


## Type
SecureValue

## Related pages
