# auth.sendCode
Send the verification code for login

```
auth.sentCode#5e002502 flags:# type:auth.SentCodeType phone_code_hash:string next_type:flags.1?auth.CodeType timeout:flags.2?int = auth.SentCode;
auth.sentCodeSuccess#2390fe44 authorization:auth.Authorization = auth.SentCode;
---functions---
auth.sendCode#a677244f phone_number:string api_id:int api_hash:string settings:CodeSettings = auth.SentCode;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| phone_number | string | Phone number in international format |
| api_id | int | Application identifier (see App configuration) |
| api_hash | string | Application secret hash (see App configuration) |
| settings | CodeSettings | Settings for the code type to send |


## Result
auth.SentCode

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | API_ID_INVALID | API ID invalid. |
| 400 | API_ID_PUBLISHED_FLOOD | This API id was published somewhere, you can't use it now. |
| 500 | AUTH_RESTART | Restart the authorization process. |
| 400 | PHONE_NUMBER_APP_SIGNUP_FORBIDDEN | You can't sign up using this app. |
| 400 | PHONE_NUMBER_BANNED | The provided phone number is banned from telegram. |
| 400 | PHONE_NUMBER_FLOOD | You asked for the code too many times. |
| 406 | PHONE_NUMBER_INVALID | The phone number is invalid. |
| 406 | PHONE_PASSWORD_FLOOD | You have tried logging in too many times. |
| 400 | PHONE_PASSWORD_PROTECTED | This phone is password protected. |
| 400 | SMS_CODE_CREATE_FAILED | An error occurred while creating the SMS code. |

