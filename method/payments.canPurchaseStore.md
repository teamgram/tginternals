# payments.canPurchaseStore
Checks whether a purchase is possible. Must be called before in-store purchase, official apps only.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
payments.canPurchaseStore#4fdc5ea7 purpose:InputStorePaymentPurpose = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| purpose | InputStorePaymentPurpose | Payment purpose. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | INPUT_PURPOSE_INVALID | The specified payment purpose is invalid. |
| 406 | PREMIUM_CURRENTLY_UNAVAILABLE | You cannot currently purchase a Premium subscription. |

