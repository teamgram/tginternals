# payments.botCancelStarsSubscription
Cancel a bot subscription

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
payments.botCancelStarsSubscription#6dfa0622 flags:# restore:flags.0?true user_id:InputUser charge_id:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| restore | flags.0?true | If not set, disables autorenewal of the subscriptions, and prevents the user from reactivating the subscription once the current period expires: a subscription cancelled by the bot will have the starsSubscription.bot_canceled flag set.  The bot can can partially undo this operation by setting this flag: this will allow the user to reactivate the subscription. |
| user_id | InputUser | The ID of the user whose subscription should be (un)cancelled |
| charge_id | string | The provider_charge_id from the messageActionPaymentSentMe service message sent to the bot for the first subscription payment. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHARGE_ID_INVALID | The specified charge_id is invalid. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

