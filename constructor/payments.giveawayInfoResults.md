# payments.giveawayInfoResults
A giveaway has ended.

```
payments.giveawayInfoResults#cd5570 flags:# winner:flags.0?true refunded:flags.1?true start_date:int gift_code_slug:flags.0?string finish_date:int winners_count:int activated_count:int = payments.GiveawayInfo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| winner | flags.0?true | Whether we're one of the winners of this giveaway. |
| refunded | flags.1?true | Whether the giveaway was canceled and was fully refunded. |
| start_date | int | Start date of the giveaway |
| gift_code_slug | flags.0?string | If we're one of the winners of this giveaway, contains the Premium gift code, see here » for more info on the full giveaway flow. |
| finish_date | int | End date of the giveaway. May be bigger than the end date specified in parameters of the giveaway. |
| winners_count | int | Number of winners in the giveaway |
| activated_count | int | Number of winners, which activated their gift codes. |


## Type
payments.GiveawayInfo

## Related pages
