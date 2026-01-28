# payments.CheckCanSendGiftResult
Specifies if a gift can or cannot be sent.

```
payments.checkCanSendGiftResultOk#374fa7ad = payments.CheckCanSendGiftResult;
payments.checkCanSendGiftResultFail#d5e58274 reason:TextWithEntities = payments.CheckCanSendGiftResult;

---functions---

payments.checkCanSendGift#c0c4edc9 gift_id:long = payments.CheckCanSendGiftResult;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| payments.checkCanSendGiftResultOk | The specified gift can be sent. |
| payments.checkCanSendGiftResultFail | The specified gift cannot be sent yet for the specified reason. |


## Methods
| Method | Description |
| ---- | ----------- |
| payments.checkCanSendGift | Check if the specified gift » can be sent. |


