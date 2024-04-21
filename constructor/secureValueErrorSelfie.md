# secureValueErrorSelfie
Represents an issue with the selfie with a document. The error is considered resolved when the file with the selfie changes.

```
secureValueErrorSelfie#e537ced6 type:SecureValueType file_hash:bytes text:string = SecureValueError;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| type | SecureValueType | One of secureValueTypePassport, secureValueTypeDriverLicense, secureValueTypeIdentityCard, secureValueTypeInternalPassport |
| file_hash | bytes | File hash |
| text | string | Error message |


## Type
SecureValueError

## Related pages
