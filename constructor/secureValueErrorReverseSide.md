# secureValueErrorReverseSide
Represents an issue with the reverse side of a document. The error is considered resolved when the file with reverse side of the document changes.

```
secureValueErrorReverseSide#868a2aa5 type:SecureValueType file_hash:bytes text:string = SecureValueError;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| type | SecureValueType | One of secureValueTypeDriverLicense, secureValueTypeIdentityCard |
| file_hash | bytes | File hash |
| text | string | Error message |


## Type
SecureValueError

## Related pages
