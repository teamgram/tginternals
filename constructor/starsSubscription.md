# starsSubscription
Represents a Telegram Star subscription ».

```
starsSubscription#2e6eab1a flags:# canceled:flags.0?true can_refulfill:flags.1?true missing_balance:flags.2?true bot_canceled:flags.7?true id:string peer:Peer until_date:int pricing:StarsSubscriptionPricing chat_invite_hash:flags.3?string title:flags.4?string photo:flags.5?WebDocument invoice_slug:flags.6?string = StarsSubscription;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| canceled | flags.0?true | Whether this subscription was cancelled. |
| can_refulfill | flags.1?true | Whether we left the associated private channel, but we can still rejoin it using payments.fulfillStarsSubscription because the current subscription period hasn't expired yet. |
| missing_balance | flags.2?true | Whether this subscription has expired because there are not enough stars on the user's balance to extend it. |
| bot_canceled | flags.7?true | Set if this bot subscription was cancelled by the bot |
| id | string | Subscription ID. |
| peer | Peer | Identifier of the associated private chat. |
| until_date | int | Expiration date of the current subscription period. |
| pricing | StarsSubscriptionPricing | Pricing of the subscription in Telegram Stars. |
| chat_invite_hash | flags.3?string | Invitation link, used to renew the subscription after cancellation or expiration. |
| title | flags.4?string | For bot subscriptions, the title of the subscription invoice |
| photo | flags.5?WebDocument | For bot subscriptions, the photo from the subscription invoice |
| invoice_slug | flags.6?string | For bot subscriptions, the identifier of the subscription invoice |


## Type
StarsSubscription

## Related pages
