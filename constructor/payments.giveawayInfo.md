# payments.giveawayInfo
Contains info about an ongoing giveaway.

```
payments.giveawayInfo#4367daa0 flags:# participating:flags.0?true preparing_results:flags.3?true start_date:int joined_too_early_date:flags.1?int admin_disallowed_chat_id:flags.2?long disallowed_country:flags.4?string = payments.GiveawayInfo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| participating | flags.0?true | The current user is participating in the giveaway. |
| preparing_results | flags.3?true | If set, the giveaway has ended and the results are being prepared. |
| start_date | int | When was the giveaway started |
| joined_too_early_date | flags.1?int | The current user can't participate in the giveaway, because they were already a member of the channel when the giveaway started, and the only_new_subscribers was set when starting the giveaway. |
| admin_disallowed_chat_id | flags.2?long | If set, the current user can't participate in the giveaway, because they are an administrator in one of the channels (ID specified in this flag) that created the giveaway. |
| disallowed_country | flags.4?string | If set, the current user can't participate in this giveaway, because their phone number is from the specified disallowed country (specified as a two-letter ISO 3166-1 alpha-2 country code). |


## Type


## Related pages
