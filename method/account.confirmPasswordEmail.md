# account.confirmPasswordEmail
Verify an email to use as 2FA recovery method.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.confirmPasswordEmail#8fdf1920 code:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| code | string | The phone code that was received after setting a recovery email |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CODE_INVALID | Code invalid. |
| 400 | EMAIL_HASH_EXPIRED | Email hash expired. |

