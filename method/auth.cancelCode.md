# auth.cancelCode
Cancel the login verification code

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
auth.cancelCode#1f040578 phone_number:string phone_code_hash:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| phone_number | string | Phone number |
| phone_code_hash | string | Phone code hash from auth.sendCode |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PHONE_CODE_EXPIRED | The phone code you provided has expired. |
| 406 | PHONE_NUMBER_INVALID | The phone number is invalid. |

