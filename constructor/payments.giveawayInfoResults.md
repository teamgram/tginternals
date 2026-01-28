# payments.giveawayInfoResults
A giveaway has ended.

```
payments.giveawayInfoResults#e175e66f flags:# winner:flags.0?true refunded:flags.1?true start_date:int gift_code_slug:flags.3?string stars_prize:flags.4?long finish_date:int winners_count:int activated_count:flags.2?int = payments.GiveawayInfo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| winner | flags.0?true | Whether we're one of the winners of this giveaway. |
| refunded | flags.1?true | Whether the giveaway was canceled and was fully refunded. |
| start_date | int | Start date of the giveaway |
| gift_code_slug | flags.3?string | If we're one of the winners of this giveaway, contains the Premium gift code, see here » for more info on the full giveaway flow. |
| stars_prize | flags.4?long | If we're one of the winners of this Telegram Star giveaway, the number Telegram Stars we won. |
| finish_date | int | End date of the giveaway. May be bigger than the end date specified in parameters of the giveaway. |
| winners_count | int | Number of winners in the giveaway |
| activated_count | flags.2?int | Number of winners, which activated their gift codes. |


## Type
payments.GiveawayInfo

## Related pages
