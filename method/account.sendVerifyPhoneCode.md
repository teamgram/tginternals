# account.sendVerifyPhoneCode
Send the verification phone code for telegram passport.

```
auth.sentCode#5e002502 flags:# type:auth.SentCodeType phone_code_hash:string next_type:flags.1?auth.CodeType timeout:flags.2?int = auth.SentCode;
auth.sentCodeSuccess#2390fe44 authorization:auth.Authorization = auth.SentCode;
---functions---
account.sendVerifyPhoneCode#a5a356f9 phone_number:string settings:CodeSettings = auth.SentCode;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| phone_number | string | The phone number to verify |
| settings | CodeSettings | Phone code settings |


## Result
auth.SentCode

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PHONE_NUMBER_INVALID | The phone number is invalid. |

