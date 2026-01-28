# bots.updateStarRefProgram
Create, edit or delete the affiliate program of a bot we own

```
starRefProgram#dd0c66f2 flags:# bot_id:long commission_permille:int duration_months:flags.0?int end_date:flags.1?int daily_revenue_per_user:flags.2?StarsAmount = StarRefProgram;
---functions---
bots.updateStarRefProgram#778b5ab3 flags:# bot:InputUser commission_permille:int duration_months:flags.0?int = StarRefProgram;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| bot | InputUser | The bot |
| commission_permille | int | The permille commission rate: it indicates the share of Telegram Stars received by affiliates for every transaction made by users they referred inside of the bot.    The minimum and maximum values for this parameter are contained in the starref_min_commission_permille and starref_max_commission_permille client configuration parameters.   Can be 0 to terminate the affiliate program.  Both the duration and the commission may only be raised after creation of the program: to lower them, the program must first be terminated and a new one created. |
| duration_months | flags.0?int | Indicates the duration of the affiliate program; if not set, there is no expiration date. |


## Result
StarRefProgram

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_INVALID | This is not a valid bot. |
| 400 | STARREF_AWAITING_END | The previous referral program was terminated less than 24 hours ago: further changes can be made after the date specified in userFull.starref_program.end_date. |
| 400 | STARREF_PERMILLE_INVALID | The specified commission_permille is invalid: the minimum and maximum values for this parameter are contained in the starref_min_commission_permille and starref_max_commission_permille client configuration parameters. |
| 400 | STARREF_PERMILLE_TOO_LOW | The specified commission_permille is too low: the minimum and maximum values for this parameter are contained in the starref_min_commission_permille and starref_max_commission_permille client configuration parameters. |

