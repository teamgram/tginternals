# account.confirmPhone
Confirm a phone number to cancel account deletion, for more info click here »

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.confirmPhone#5f2178c3 phone_code_hash:string phone_code:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| phone_code_hash | string | Phone code hash, for more info click here » |
| phone_code | string | SMS code, for more info click here » |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CODE_HASH_INVALID | Code hash invalid. |
| 400 | PHONE_CODE_EMPTY | phone_code is missing. |

