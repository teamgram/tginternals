# payments.getStarsTransactions
Fetch Telegram Stars transactions.

```
payments.starsStatus#6c9ce8ed flags:# balance:StarsAmount subscriptions:flags.1?Vector<StarsSubscription> subscriptions_next_offset:flags.2?string subscriptions_missing_balance:flags.4?long history:flags.3?Vector<StarsTransaction> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = payments.StarsStatus;
---functions---
payments.getStarsTransactions#69da4557 flags:# inbound:flags.0?true outbound:flags.1?true ascending:flags.2?true ton:flags.4?true subscription_id:flags.3?string peer:InputPeer offset:string limit:int = payments.StarsStatus;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| inbound | flags.0?true | If set, fetches only incoming transactions. |
| outbound | flags.1?true | If set, fetches only outgoing transactions. |
| ascending | flags.2?true | Return transactions in ascending order by date (instead of descending order by date). |
| ton | flags.4?true | If set, returns the channel/ad revenue transactions in nanotons, instead. |
| subscription_id | flags.3?string | If set, fetches only transactions for the specified Telegram Star subscription ». |
| peer | InputPeer | Fetch the transaction history of the peer (inputPeerSelf or a bot we own). |
| offset | string | Offset for pagination, obtained from the returned next_offset, initially an empty string ». |
| limit | int | Maximum number of results to return, see pagination |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | SUBSCRIPTION_ID_INVALID | The specified subscription_id is invalid. |

