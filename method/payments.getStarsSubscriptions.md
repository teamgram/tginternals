# payments.getStarsSubscriptions
Obtain a list of active, expired or cancelled Telegram Star subscriptions ».

```
payments.starsStatus#6c9ce8ed flags:# balance:StarsAmount subscriptions:flags.1?Vector<StarsSubscription> subscriptions_next_offset:flags.2?string subscriptions_missing_balance:flags.4?long history:flags.3?Vector<StarsTransaction> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = payments.StarsStatus;
---functions---
payments.getStarsSubscriptions#32512c5 flags:# missing_balance:flags.0?true peer:InputPeer offset:string = payments.StarsStatus;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| missing_balance | flags.0?true | Whether to return only subscriptions expired due to an excessively low Telegram Star balance. |
| peer | InputPeer | Always pass inputPeerSelf. |
| offset | string | Offset for pagination, taken from payments.starsStatus.subscriptions_next_offset. |


## Result
payments.StarsStatus

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

