# auth.resetLoginEmail
Reset the login email ».

```
auth.sentCode#5e002502 flags:# type:auth.SentCodeType phone_code_hash:string next_type:flags.1?auth.CodeType timeout:flags.2?int = auth.SentCode;
auth.sentCodeSuccess#2390fe44 authorization:auth.Authorization = auth.SentCode;
---functions---
auth.resetLoginEmail#7e960193 phone_number:string phone_code_hash:string = auth.SentCode;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| phone_number | string | Phone number of the account |
| phone_code_hash | string | Phone code hash, obtained as described in the documentation » |


## Result
auth.SentCode

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PHONE_NUMBER_INVALID | The phone number is invalid. |
| 400 | TASK_ALREADY_EXISTS | An email reset was already requested. |

