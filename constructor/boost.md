# boost
Info about one or more boosts applied by a specific user.

```
boost#2a1c8c71 flags:# gift:flags.1?true giveaway:flags.2?true unclaimed:flags.3?true id:string user_id:flags.0?long giveaway_msg_id:flags.2?int date:int expires:int used_gift_slug:flags.4?string multiplier:flags.5?int = Boost;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| gift | flags.1?true | Whether this boost was applied because the channel directly gifted a subscription to the user. |
| giveaway | flags.2?true | Whether this boost was applied because the user was chosen in a giveaway started by the channel. |
| unclaimed | flags.3?true | If set, the user hasn't yet invoked payments.applyGiftCode to claim a subscription gifted directly or in a giveaway by the channel. |
| id | string | Unique ID for this set of boosts. |
| user_id | flags.0?long | ID of the user that applied the boost. |
| giveaway_msg_id | flags.2?int | The message ID of the giveaway |
| date | int | When was the boost applied |
| expires | int | When does the boost expire |
| used_gift_slug | flags.4?string | The created Telegram Premium gift code, only set if either gift or giveaway are set AND it is either a gift code for the currently logged in user or if it was already claimed. |
| multiplier | flags.5?int | If set, this boost counts as multiplier boosts, otherwise it counts as a single boost. |


## Type
Boost

## Related pages
