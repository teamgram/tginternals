# auth.requestFirebaseSms
Request an SMS code via Firebase.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
auth.requestFirebaseSms#89464b50 flags:# phone_number:string phone_code_hash:string safety_net_token:flags.0?string ios_push_secret:flags.1?string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| phone_number | string | Phone number |
| phone_code_hash | string | Phone code hash returned by auth.sendCode |
| safety_net_token | flags.0?string | On Android, a JWS object obtained as described in the auth documentation » |
| ios_push_secret | flags.1?string | Secret token received via an apple push notification |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PHONE_NUMBER_INVALID | The phone number is invalid. |

