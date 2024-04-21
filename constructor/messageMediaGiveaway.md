# messageMediaGiveaway
Contains info about a giveaway, see here » for more info.

```
messageMediaGiveaway#daad85b0 flags:# only_new_subscribers:flags.0?true winners_are_visible:flags.2?true channels:Vector<long> countries_iso2:flags.1?Vector<string> prize_description:flags.3?string quantity:int months:int until_date:int = MessageMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| only_new_subscribers | flags.0?true | If set, only new subscribers starting from the giveaway creation date will be able to participate to the giveaway. |
| winners_are_visible | flags.2?true | If set, giveaway winners are public and will be listed in a messageMediaGiveawayResults message that will be automatically sent to the channel once the giveaway ends. |
| channels | Vector<long> | The channels that the user must join to participate in the giveaway. |
| countries_iso2 | flags.1?Vector<string> | If set, only users residing in these countries can participate in the giveaway, (specified as a list of two-letter ISO 3166-1 alpha-2 country codes); otherwise there are no country-based limitations. |
| prize_description | flags.3?string | Can contain a textual description of additional giveaway prizes. |
| quantity | int | Number of Telegram Premium subscriptions given away. |
| months | int | Duration in months of each Telegram Premium subscription in the giveaway. |
| until_date | int | The end date of the giveaway. |


## Type
MessageMedia

## Related pages
