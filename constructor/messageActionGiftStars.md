# messageActionGiftStars
You gifted or were gifted some Telegram Stars.

```
messageActionGiftStars#45d5b021 flags:# currency:string amount:long stars:long crypto_currency:flags.0?string crypto_amount:flags.0?long transaction_id:flags.1?string = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| currency | string | Three-letter ISO 4217 currency code |
| amount | long | Price of the gift in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |
| stars | long | Amount of gifted stars |
| crypto_currency | flags.0?string | If the gift was bought using a cryptocurrency, the cryptocurrency name. |
| crypto_amount | flags.0?long | If the gift was bought using a cryptocurrency, price of the gift in the smallest units of a cryptocurrency. |
| transaction_id | flags.1?string | Identifier of the transaction, only visible to the receiver of the gift. |


## Type


## Related pages
