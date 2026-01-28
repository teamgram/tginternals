# payments.checkCanSendGift
Check if the specified gift » can be sent.

```
payments.checkCanSendGiftResultOk#374fa7ad = payments.CheckCanSendGiftResult;
payments.checkCanSendGiftResultFail#d5e58274 reason:TextWithEntities = payments.CheckCanSendGiftResult;
---functions---
payments.checkCanSendGift#c0c4edc9 gift_id:long = payments.CheckCanSendGiftResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| gift_id | long | Gift ID. |


## Result
payments.CheckCanSendGiftResult

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | STARGIFT_INVALID | The passed gift is invalid. |

