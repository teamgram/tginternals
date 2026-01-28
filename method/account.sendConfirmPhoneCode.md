# account.sendConfirmPhoneCode
Send confirmation code to cancel account deletion, for more info click here »

```
auth.sentCode#5e002502 flags:# type:auth.SentCodeType phone_code_hash:string next_type:flags.1?auth.CodeType timeout:flags.2?int = auth.SentCode;
auth.sentCodeSuccess#2390fe44 authorization:auth.Authorization = auth.SentCode;
auth.sentCodePaymentRequired#d7a2fcf9 store_product:string phone_code_hash:string support_email_address:string support_email_subject:string = auth.SentCode;
---functions---
account.sendConfirmPhoneCode#1b3faa88 hash:string settings:CodeSettings = auth.SentCode;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| hash | string | The hash from the service notification, for more info click here » |
| settings | CodeSettings | Phone code settings |


## Result
auth.SentCode

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | HASH_INVALID | The provided hash is invalid. |

