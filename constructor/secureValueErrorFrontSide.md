# secureValueErrorFrontSide
Represents an issue with the front side of a document. The error is considered resolved when the file with the front side of the document changes.

```
secureValueErrorFrontSide#be3dfa type:SecureValueType file_hash:bytes text:string = SecureValueError;
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
