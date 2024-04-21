# myBoost
Contains information about a single boost slot ».

```
myBoost#c448415c flags:# slot:int peer:flags.0?Peer date:int expires:int cooldown_until_date:flags.1?int = MyBoost;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| slot | int | Boost slot ID » |
| peer | flags.0?Peer | If set, indicates this slot is currently occupied, i.e. we are boosting this peer.  Note that we can assign multiple boost slots to the same peer. |
| date | int | When (unixtime) we started boosting the peer, 0 otherwise. |
| expires | int | Indicates the (unixtime) expiration date of the boost in peer (0 if peer is not set). |
| cooldown_until_date | flags.1?int | If peer is set, indicates the (unixtime) date after which this boost can be reassigned to another channel. |


## Type
MyBoost

## Related pages
