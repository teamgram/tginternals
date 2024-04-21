# auth.sentCode
Contains info about a sent verification code.

```
auth.sentCode#5e002502 flags:# type:auth.SentCodeType phone_code_hash:string next_type:flags.1?auth.CodeType timeout:flags.2?int = auth.SentCode;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| type | auth.SentCodeType | Phone code type |
| phone_code_hash | string | Phone code hash, to be stored and later re-used with auth.signIn |
| next_type | flags.1?auth.CodeType | Phone code type that will be sent next, if the phone code is not received within timeout seconds: to send it use auth.resendCode |
| timeout | flags.2?int | Timeout for reception of the phone code |


## Type
auth.SentCode

## Related pages
