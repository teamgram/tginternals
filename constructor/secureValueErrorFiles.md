# secureValueErrorFiles
Represents an issue with a list of scans. The error is considered resolved when the list of files containing the scans changes.

```
secureValueErrorFiles#666220e9 type:SecureValueType file_hash:Vector<bytes> text:string = SecureValueError;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| type | SecureValueType | One of secureValueTypeUtilityBill, secureValueTypeBankStatement, secureValueTypeRentalAgreement, secureValueTypePassportRegistration, secureValueTypeTemporaryRegistration |
| file_hash | Vector<bytes> | File hash |
| text | string | Error message |


## Type
SecureValueError

## Related pages
