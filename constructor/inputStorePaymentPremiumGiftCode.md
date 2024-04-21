# inputStorePaymentPremiumGiftCode
Used to gift Telegram Premium subscriptions only to some specific subscribers of a channel or to some of our contacts, see here » for more info on giveaways and gifts.

```
inputStorePaymentPremiumGiftCode#a3805f3f flags:# users:Vector<InputUser> boost_peer:flags.0?InputPeer currency:string amount:long = InputStorePaymentPurpose;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| users | Vector<InputUser> | The users that will receive the Telegram Premium subscriptions. |
| boost_peer | flags.0?InputPeer | If set, the gifts will be sent on behalf of a channel we are an admin of, which will also assign some boosts to it. Otherwise, the gift will be sent directly from the currently logged in users, and we will gain some extra boost slots. See here » for more info on giveaways and gifts. |
| currency | string | Three-letter ISO 4217 currency code |
| amount | long | Total price in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |


## Type
InputStorePaymentPurpose

## Related pages
