# messageActionGiftCode
Contains a Telegram Premium giftcode link.

```
messageActionGiftCode#678c2e09 flags:# via_giveaway:flags.0?true unclaimed:flags.2?true boost_peer:flags.1?Peer months:int slug:string currency:flags.2?string amount:flags.2?long crypto_currency:flags.3?string crypto_amount:flags.3?long = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| via_giveaway | flags.0?true | If set, this gift code was received from a giveaway » started by a channel we're subscribed to. |
| unclaimed | flags.2?true | If set, the link was not redeemed yet. |
| boost_peer | flags.1?Peer | Identifier of the channel that created the gift code either directly or through a giveaway: if we import this giftcode link, we will also automatically boost this channel. |
| months | int | Duration in months of the gifted Telegram Premium subscription. |
| slug | string | Slug of the Telegram Premium giftcode link |
| currency | flags.2?string | Three-letter ISO 4217 currency code |
| amount | flags.2?long | Total price in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |
| crypto_currency | flags.3?string | If set, the gift was made using the specified cryptocurrency. |
| crypto_amount | flags.3?long | If crypto_currency is set, contains the paid amount, in the smallest units of the cryptocurrency. |


## Type
MessageAction

## Related pages
