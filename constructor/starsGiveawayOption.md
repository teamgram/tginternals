# starsGiveawayOption
Contains info about a Telegram Star giveaway option.

```
starsGiveawayOption#94ce852a flags:# extended:flags.0?true default:flags.1?true stars:long yearly_boosts:int store_product:flags.2?string currency:string amount:long winners:Vector<StarsGiveawayWinnersOption> = StarsGiveawayOption;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| extended | flags.0?true | If set, this option must only be shown in the full list of giveaway options (i.e. they must be added to the list only when the user clicks on the expand button). |
| default | flags.1?true | If set, this option must be pre-selected by default in the option list. |
| stars | long | The number of Telegram Stars that will be distributed among winners |
| yearly_boosts | int | Number of times the chat will be boosted for one year if the inputStorePaymentStarsGiveaway.boost_peer flag is populated |
| store_product | flags.2?string | Identifier of the store product associated with the option, official apps only. |
| currency | string | Three-letter ISO 4217 currency code |
| amount | long | Total price in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |
| winners | Vector<StarsGiveawayWinnersOption> | Allowed options for the number of giveaway winners. |


## Type
StarsGiveawayOption

## Related pages
