# account.sendChangePhoneCode
Verify a new phone number to associate to the current account

```
auth.sentCode#5e002502 flags:# type:auth.SentCodeType phone_code_hash:string next_type:flags.1?auth.CodeType timeout:flags.2?int = auth.SentCode;
auth.sentCodeSuccess#2390fe44 authorization:auth.Authorization = auth.SentCode;
---functions---
account.sendChangePhoneCode#82574ae5 phone_number:string settings:CodeSettings = auth.SentCode;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| phone_number | string | New phone number |
| settings | CodeSettings | Phone code settings |


## Result
auth.SentCode

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 406 | FRESH_CHANGE_PHONE_FORBIDDEN | You can't change phone number right after logging in, please wait at least 24 hours. |
| 400 | PHONE_NUMBER_BANNED | The provided phone number is banned from telegram. |
| 406 | PHONE_NUMBER_INVALID | The phone number is invalid. |
| 400 | PHONE_NUMBER_OCCUPIED | The phone number is already in use. |

