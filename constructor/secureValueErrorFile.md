# secureValueErrorFile
Represents an issue with a document scan. The error is considered resolved when the file with the document scan changes.

```
secureValueErrorFile#7a700873 type:SecureValueType file_hash:bytes text:string = SecureValueError;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| type | SecureValueType | One of secureValueTypeUtilityBill, secureValueTypeBankStatement, secureValueTypeRentalAgreement, secureValueTypePassportRegistration, secureValueTypeTemporaryRegistration |
| file_hash | bytes | File hash |
| text | string | Error message |


## Type
SecureValueError

## Related pages
