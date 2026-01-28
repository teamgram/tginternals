# payments.getStarsStatus
Get the current Telegram Stars balance of the current account (with peer=inputPeerSelf), or the stars balance of the bot specified in peer.

```
payments.starsStatus#6c9ce8ed flags:# balance:StarsAmount subscriptions:flags.1?Vector<StarsSubscription> subscriptions_next_offset:flags.2?string subscriptions_missing_balance:flags.4?long history:flags.3?Vector<StarsTransaction> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = payments.StarsStatus;
---functions---
payments.getStarsStatus#4ea9b3bf flags:# ton:flags.0?true peer:InputPeer = payments.StarsStatus;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| ton | flags.0?true | If set, returns the channel/ad revenue balance in nanotons. |
| peer | InputPeer | Peer of which to get the balance. |


## Result
payments.StarsStatus

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | BOT_ACCESS_FORBIDDEN | The specified method can be used over a business connection for some operations, but the specified query attempted an operation that is not allowed over a business connection. |
| 400 | BUSINESS_CONNECTION_INVALID | The connection_id passed to the wrapping invokeWithBusinessConnection call is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

