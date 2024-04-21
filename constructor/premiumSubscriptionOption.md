# premiumSubscriptionOption
Describes a Telegram Premium subscription option

```
premiumSubscriptionOption#5f2d1df2 flags:# current:flags.1?true can_purchase_upgrade:flags.2?true transaction:flags.3?string months:int currency:string amount:long bot_url:string store_product:flags.0?string = PremiumSubscriptionOption;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| current | flags.1?true | Whether this subscription option is currently in use. |
| can_purchase_upgrade | flags.2?true | Whether this subscription option can be used to upgrade the existing Telegram Premium subscription. When upgrading Telegram Premium subscriptions bought through stores, make sure that the store transaction ID is equal to transaction, to avoid upgrading someone else's account, if the client is currently logged into multiple accounts. |
| transaction | flags.3?string | Identifier of the last in-store transaction for the currently used subscription on the current account. |
| months | int | Duration of subscription in months |
| currency | string | Three-letter ISO 4217 currency code |
| amount | long | Total price in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |
| bot_url | string | Deep link used to initiate payment |
| store_product | flags.0?string | Store product ID, only for official apps |


## Type
PremiumSubscriptionOption

## Related pages
