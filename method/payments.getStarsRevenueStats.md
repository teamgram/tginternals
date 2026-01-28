# payments.getStarsRevenueStats
Get Telegram Star revenue statistics ».

```
payments.starsRevenueStats#6c207376 flags:# top_hours_graph:flags.0?StatsGraph revenue_graph:StatsGraph status:StarsRevenueStatus usd_rate:double = payments.StarsRevenueStats;
---functions---
payments.getStarsRevenueStats#d91ffad6 flags:# dark:flags.0?true ton:flags.1?true peer:InputPeer = payments.StarsRevenueStats;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| dark | flags.0?true | Whether to enable dark theme for graph colors |
| ton | flags.1?true | If set, fetches channel/bot ad revenue statistics in TON. |
| peer | InputPeer | Get statistics for the specified bot, channel or ourselves (inputPeerSelf). |


## Result
payments.StarsRevenueStats

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

