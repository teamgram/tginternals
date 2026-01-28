# payments.starsStatus
Info about the current Telegram Star subscriptions, balance and transaction history ».

```
payments.starsStatus#6c9ce8ed flags:# balance:StarsAmount subscriptions:flags.1?Vector<StarsSubscription> subscriptions_next_offset:flags.2?string subscriptions_missing_balance:flags.4?long history:flags.3?Vector<StarsTransaction> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = payments.StarsStatus;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| balance | StarsAmount | Current Telegram Star balance. |
| subscriptions | flags.1?Vector<StarsSubscription> | Info about current Telegram Star subscriptions, only returned when invoking payments.getStarsTransactions and payments.getStarsSubscriptions. |
| subscriptions_next_offset | flags.2?string | Offset for pagination of subscriptions: only usable and returned when invoking payments.getStarsSubscriptions. |
| subscriptions_missing_balance | flags.4?long | The number of Telegram Stars the user should buy to be able to extend expired subscriptions soon (i.e. the current balance is not enough to extend all expired subscriptions). |
| history | flags.3?Vector<StarsTransaction> | List of Telegram Star transactions (partial if next_offset is set). |
| next_offset | flags.0?string | Offset to use to fetch more transactions from the transaction history using payments.getStarsTransactions. |
| chats | Vector<Chat> | Chats mentioned in history. |
| users | Vector<User> | Users mentioned in history. |


## Type
payments.StarsStatus

## Related pages
