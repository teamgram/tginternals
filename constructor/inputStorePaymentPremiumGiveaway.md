# inputStorePaymentPremiumGiveaway
Used to pay for a giveaway, see here » for more info.

```
inputStorePaymentPremiumGiveaway#160544ca flags:# only_new_subscribers:flags.0?true winners_are_visible:flags.3?true boost_peer:InputPeer additional_peers:flags.1?Vector<InputPeer> countries_iso2:flags.2?Vector<string> prize_description:flags.4?string random_id:long until_date:int currency:string amount:long = InputStorePaymentPurpose;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| only_new_subscribers | flags.0?true | If set, only new subscribers starting from the giveaway creation date will be able to participate to the giveaway. |
| winners_are_visible | flags.3?true | If set, giveaway winners are public and will be listed in a messageMediaGiveawayResults message that will be automatically sent to the channel once the giveaway ends. |
| boost_peer | InputPeer | The channel starting the giveaway, that the user must join to participate, that will receive the giveaway boosts; see here » for more info on giveaways. |
| additional_peers | flags.1?Vector<InputPeer> | Additional channels that the user must join to participate to the giveaway can be specified here. |
| countries_iso2 | flags.2?Vector<string> | The set of users that can participate to the giveaway can be restricted by passing here an explicit whitelist of up to giveaway_countries_max countries, specified as two-letter ISO 3166-1 alpha-2 country codes. |
| prize_description | flags.4?string | Can contain a textual description of additional giveaway prizes. |
| random_id | long | Random ID to avoid resending the giveaway |
| until_date | int | The end date of the giveaway, must be at most giveaway_period_max seconds in the future; see here » for more info on giveaways. |
| currency | string | Three-letter ISO 4217 currency code |
| amount | long | Total price in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |


## Type
InputStorePaymentPurpose

## Related pages
