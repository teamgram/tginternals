# starRefProgram
Indo about an affiliate program offered by a bot

```
starRefProgram#dd0c66f2 flags:# bot_id:long commission_permille:int duration_months:flags.0?int end_date:flags.1?int daily_revenue_per_user:flags.2?StarsAmount = StarRefProgram;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| bot_id | long | ID of the bot that offers the program |
| commission_permille | int | An affiliate gets a commission of starRefProgram.commission_permille‰ Telegram Stars for every mini app transaction made by users they refer |
| duration_months | flags.0?int | An affiliate gets a commission for every mini app transaction made by users they refer, for duration_months months after a referral link is imported, starting the bot for the first time |
| end_date | flags.1?int | Point in time (Unix timestamp) when the affiliate program will be closed (optional, if not set the affiliate program isn't scheduled to be closed) |
| daily_revenue_per_user | flags.2?StarsAmount | The amount of daily revenue per user in Telegram Stars of the bot that created the affiliate program. To obtain the approximated revenue per referred user, multiply this value by commission_permille and divide by 1000. |


## Type
StarRefProgram

## Related pages
