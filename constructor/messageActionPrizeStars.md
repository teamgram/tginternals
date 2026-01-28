# messageActionPrizeStars
You won some Telegram Stars in a Telegram Star giveaway ».

```
messageActionPrizeStars#b00c47a2 flags:# unclaimed:flags.0?true stars:long transaction_id:string boost_peer:Peer giveaway_msg_id:int = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| unclaimed | flags.0?true | If set, this indicates the reverse transaction that refunds the remaining stars to the creator of a giveaway if, when the giveaway ends, the number of members in the channel is smaller than the number of winners in the giveaway. |
| stars | long | The number of Telegram Stars you won |
| transaction_id | string | ID of the telegram star transaction. |
| boost_peer | Peer | Identifier of the peer that was automatically boosted by the winners of the giveaway. |
| giveaway_msg_id | int | ID of the message containing the messageMediaGiveaway |


## Type


## Related pages
