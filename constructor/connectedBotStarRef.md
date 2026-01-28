# connectedBotStarRef
Info about an active affiliate program we have with a Mini App

```
connectedBotStarRef#19a13f71 flags:# revoked:flags.1?true url:string date:int bot_id:long commission_permille:int duration_months:flags.0?int participants:long revenue:long = ConnectedBotStarRef;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| revoked | flags.1?true | If set, this affiliation was revoked by the affiliate using payments.editConnectedStarRefBot, or by the affiliation program owner using bots.updateStarRefProgram |
| url | string | Referral link to be shared |
| date | int | When did we affiliate with bot_id |
| bot_id | long | ID of the mini app that created the affiliate program |
| commission_permille | int | The number of Telegram Stars received by the affiliate for each 1000 Telegram Stars received by bot_id |
| duration_months | flags.0?int | Number of months the program will be active; if not set, there is no expiration date. |
| participants | long | The number of users that used the affiliate program |
| revenue | long | The number of Telegram Stars that were earned by the affiliate program |


## Type
ConnectedBotStarRef

## Related pages
