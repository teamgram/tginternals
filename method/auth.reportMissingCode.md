# auth.reportMissingCode
Official apps only, reports that the SMS authentication code wasn't delivered.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
auth.reportMissingCode#cb9deff6 phone_number:string phone_code_hash:string mnc:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| phone_number | string | Phone number where we were supposed to receive the code |
| phone_code_hash | string | The phone code hash obtained from auth.sendCode |
| mnc | string | MNC of the current network operator. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PHONE_NUMBER_INVALID | The phone number is invalid. |

