# account.verifyPhone
Verify a phone number for telegram passport.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.verifyPhone#4dd3a7f6 phone_number:string phone_code_hash:string phone_code:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| phone_number | string | Phone number |
| phone_code_hash | string | Phone code hash received from the call to account.sendVerifyPhoneCode |
| phone_code | string | Code received after the call to account.sendVerifyPhoneCode |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PHONE_CODE_EMPTY | phone_code is missing. |
| 400 | PHONE_CODE_EXPIRED | The phone code you provided has expired. |
| 400 | PHONE_NUMBER_INVALID | The phone number is invalid. |

