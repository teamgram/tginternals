# payments.StarsStatus
Info about the current Telegram Star subscriptions, balance and transaction history ».

```
payments.starsStatus#6c9ce8ed flags:# balance:StarsAmount subscriptions:flags.1?Vector<StarsSubscription> subscriptions_next_offset:flags.2?string subscriptions_missing_balance:flags.4?long history:flags.3?Vector<StarsTransaction> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = payments.StarsStatus;

---functions---

payments.getStarsStatus#4ea9b3bf flags:# ton:flags.0?true peer:InputPeer = payments.StarsStatus;
payments.getStarsTransactions#69da4557 flags:# inbound:flags.0?true outbound:flags.1?true ascending:flags.2?true ton:flags.4?true subscription_id:flags.3?string peer:InputPeer offset:string limit:int = payments.StarsStatus;
payments.getStarsTransactionsByID#2dca16b8 flags:# ton:flags.0?true peer:InputPeer id:Vector<InputStarsTransaction> = payments.StarsStatus;
payments.getStarsSubscriptions#32512c5 flags:# missing_balance:flags.0?true peer:InputPeer offset:string = payments.StarsStatus;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| payments.starsStatus | Info about the current Telegram Star subscriptions, balance and transaction history ». |


## Methods
| Method | Description |
| ---- | ----------- |
| payments.getStarsStatus | Get the current Telegram Stars balance of the current account (with peer=inputPeerSelf), or the stars balance of the bot specified in peer. |
| payments.getStarsTransactions | Fetch Telegram Stars transactions.The inbound and outbound flags are mutually exclusive: if none of the two are set, both incoming and outgoing transactions are fetched. |
| payments.getStarsTransactionsByID | Obtain info about Telegram Star transactions » using specific transaction IDs. |
| payments.getStarsSubscriptions | Obtain a list of active, expired or cancelled Telegram Star subscriptions ». |


