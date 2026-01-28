# messageActionSuggestedPostRefund
A suggested post » was accepted and posted or scheduled, but either the channel deleted the posted/scheduled post before stars_suggested_post_age_min seconds have elapsed, or the user refunded the payment for the stars used to pay for the suggested post.

```
messageActionSuggestedPostRefund#69f916f8 flags:# payer_initiated:flags.0?true = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| payer_initiated | flags.0?true | If set, the user refunded the payment for the stars used to pay for the suggested post. |


## Type
MessageAction

## Related pages
