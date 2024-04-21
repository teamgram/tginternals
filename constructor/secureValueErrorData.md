# secureValueErrorData
Represents an issue in one of the data fields that was provided by the user. The error is considered resolved when the field's value changes.

```
secureValueErrorData#e8a40bd9 type:SecureValueType data_hash:bytes field:string text:string = SecureValueError;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| type | SecureValueType | The section of the user's Telegram Passport which has the error, one of secureValueTypePersonalDetails, secureValueTypePassport, secureValueTypeDriverLicense, secureValueTypeIdentityCard, secureValueTypeInternalPassport, secureValueTypeAddress |
| data_hash | bytes | Data hash |
| field | string | Name of the data field which has the error |
| text | string | Error message |


## Type
SecureValueError

## Related pages
