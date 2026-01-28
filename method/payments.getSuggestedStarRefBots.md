# payments.getSuggestedStarRefBots
Obtain a list of suggested mini apps with available affiliate programs

```
payments.suggestedStarRefBots#b4d5d859 flags:# count:int suggested_bots:Vector<StarRefProgram> users:Vector<User> next_offset:flags.0?string = payments.SuggestedStarRefBots;
---functions---
payments.getSuggestedStarRefBots#d6b48f7 flags:# order_by_revenue:flags.0?true order_by_date:flags.1?true peer:InputPeer offset:string limit:int = payments.SuggestedStarRefBots;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| order_by_revenue | flags.0?true | If set, orders results by the expected revenue |
| order_by_date | flags.1?true | If set, orders results by the creation date of the affiliate program |
| peer | InputPeer | The peer that will become the affiliate: star commissions will be transferred to this peer's star balance. |
| offset | string | Offset for pagination, taken from payments.suggestedStarRefBots.next_offset, initially empty. |
| limit | int | Maximum number of results to return, see pagination |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | PEER_ID_INVALID | The provided peer id is invalid. |

