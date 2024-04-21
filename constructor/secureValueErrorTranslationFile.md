# secureValueErrorTranslationFile
Represents an issue with one of the files that constitute the translation of a document. The error is considered resolved when the file changes.

```
secureValueErrorTranslationFile#a1144770 type:SecureValueType file_hash:bytes text:string = SecureValueError;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| type | SecureValueType | One of secureValueTypePersonalDetails, secureValueTypePassport, secureValueTypeDriverLicense, secureValueTypeIdentityCard, secureValueTypeInternalPassport, secureValueTypeUtilityBill, secureValueTypeBankStatement, secureValueTypeRentalAgreement, secureValueTypePassportRegistration, secureValueTypeTemporaryRegistration |
| file_hash | bytes | File hash |
| text | string | Error message |


## Type
SecureValueError

## Related pages
