# starsRevenueStatus
Describes Telegram Star revenue balances ».

```
starsRevenueStatus#febe5491 flags:# withdrawal_enabled:flags.0?true current_balance:StarsAmount available_balance:StarsAmount overall_revenue:StarsAmount next_withdrawal_at:flags.1?int = StarsRevenueStatus;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| withdrawal_enabled | flags.0?true | If set, the user may withdraw up to available_balance stars. |
| current_balance | StarsAmount | Amount of not-yet-withdrawn Telegram Stars. |
| available_balance | StarsAmount | Amount of withdrawable Telegram Stars. |
| overall_revenue | StarsAmount | Total amount of earned Telegram Stars. |
| next_withdrawal_at | flags.1?int | Unixtime indicating when will withdrawal be available to the user. If not set, withdrawal can be started now. |


## Type
StarsRevenueStatus

## Related pages
