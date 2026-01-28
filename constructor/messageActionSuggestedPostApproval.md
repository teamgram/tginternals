# messageActionSuggestedPostApproval
A suggested post » was approved or rejected.

```
messageActionSuggestedPostApproval#ee7a1596 flags:# rejected:flags.0?true balance_too_low:flags.1?true reject_comment:flags.2?string schedule_date:flags.3?int price:flags.4?StarsAmount = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| rejected | flags.0?true | Whether the suggested post was rejected. |
| balance_too_low | flags.1?true | If set, the post was approved but the user's balance is too low to pay for the suggested post. |
| reject_comment | flags.2?string | If the suggested post was rejected, can optionally contain a rejection comment. |
| schedule_date | flags.3?int | Scheduling date. |
| price | flags.4?StarsAmount | Price for the suggested post. |


## Type
MessageAction

## Related pages
