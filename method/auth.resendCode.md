# auth.resendCode
Resend the login code via another medium, the phone code type is determined by the return value of the previous auth.sendCode/auth.resendCode: see login for more info.

```
auth.sentCode#5e002502 flags:# type:auth.SentCodeType phone_code_hash:string next_type:flags.1?auth.CodeType timeout:flags.2?int = auth.SentCode;
auth.sentCodeSuccess#2390fe44 authorization:auth.Authorization = auth.SentCode;
---functions---
auth.resendCode#3ef1a9bf phone_number:string phone_code_hash:string = auth.SentCode;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| phone_number | string | The phone number |
| phone_code_hash | string | The phone code hash obtained from auth.sendCode |


## Result
auth.SentCode

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PHONE_CODE_EMPTY | phone_code is missing. |
| 400 | PHONE_CODE_EXPIRED | The phone code you provided has expired. |
| 400 | PHONE_CODE_HASH_EMPTY | phone_code_hash is missing. |
| 406 | PHONE_NUMBER_INVALID | The phone number is invalid. |
| 406 | SEND_CODE_UNAVAILABLE | Returned when all available options for this type of number were already used (e.g. flash-call, then SMS, then this error might be returned to trigger a second resend). |

