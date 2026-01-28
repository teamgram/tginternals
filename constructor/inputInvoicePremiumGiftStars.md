# inputInvoicePremiumGiftStars
Used to gift a Telegram Premium subscription to another user, paying with Telegram Stars.

```
inputInvoicePremiumGiftStars#dabab2ef flags:# user_id:InputUser months:int message:flags.0?TextWithEntities = InputInvoice;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| user_id | InputUser | Who will receive the gifted subscription. |
| months | int | Duration of the subscription in months, must be one of the options with currency == "XTR" returned by payments.getPremiumGiftCodeOptions. |
| message | flags.0?TextWithEntities | Message attached with the gift. |


## Type
InputInvoice

## Related pages
