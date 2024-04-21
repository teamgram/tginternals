# inputSecureValue
Secure value, for more info see the passport docs »

```
inputSecureValue#db21d0a7 flags:# type:SecureValueType data:flags.0?SecureData front_side:flags.1?InputSecureFile reverse_side:flags.2?InputSecureFile selfie:flags.3?InputSecureFile translation:flags.6?Vector<InputSecureFile> files:flags.4?Vector<InputSecureFile> plain_data:flags.5?SecurePlainData = InputSecureValue;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| type | SecureValueType | Secure passport value type |
| data | flags.0?SecureData | Encrypted Telegram Passport element data |
| front_side | flags.1?InputSecureFile | Encrypted passport file with the front side of the document |
| reverse_side | flags.2?InputSecureFile | Encrypted passport file with the reverse side of the document |
| selfie | flags.3?InputSecureFile | Encrypted passport file with a selfie of the user holding the document |
| translation | flags.6?Vector<InputSecureFile> | Array of encrypted passport files with translated versions of the provided documents |
| files | flags.4?Vector<InputSecureFile> | Array of encrypted passport files with photos the of the documents |
| plain_data | flags.5?SecurePlainData | Plaintext verified passport data |


## Type
InputSecureValue

## Related pages
