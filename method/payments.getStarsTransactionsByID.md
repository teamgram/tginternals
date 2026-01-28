# payments.getStarsTransactionsByID
Obtain info about Telegram Star transactions » using specific transaction IDs.

```
payments.starsStatus#6c9ce8ed flags:# balance:StarsAmount subscriptions:flags.1?Vector<StarsSubscription> subscriptions_next_offset:flags.2?string subscriptions_missing_balance:flags.4?long history:flags.3?Vector<StarsTransaction> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = payments.StarsStatus;
---functions---
payments.getStarsTransactionsByID#2dca16b8 flags:# ton:flags.0?true peer:InputPeer id:Vector<InputStarsTransaction> = payments.StarsStatus;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| ton | flags.0?true | If set, returns channel/bot ad revenue transactions in nanotons. |
| peer | InputPeer | Channel or bot. |
| id | Vector<InputStarsTransaction> | Transaction IDs. |


## Result
payments.StarsStatus

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | TRANSACTION_ID_INVALID | The specified transaction ID is invalid. |

