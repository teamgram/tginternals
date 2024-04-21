# premium.boostsStatus
Contains info about the current boost status of a peer.

```
premium.boostsStatus#4959427a flags:# my_boost:flags.2?true level:int current_level_boosts:int boosts:int gift_boosts:flags.4?int next_level_boosts:flags.0?int premium_audience:flags.1?StatsPercentValue boost_url:string prepaid_giveaways:flags.3?Vector<PrepaidGiveaway> my_boost_slots:flags.2?Vector<int> = premium.BoostsStatus;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| my_boost | flags.2?true | Whether we're currently boosting this channel, my_boost_slots will also be set. |
| level | int | The current boost level of the channel. |
| current_level_boosts | int | The number of boosts acquired so far in the current level. |
| boosts | int | Total number of boosts acquired so far. |
| gift_boosts | flags.4?int | The number of boosts acquired from created Telegram Premium gift codes and giveaways; only returned to channel admins. |
| next_level_boosts | flags.0?int | Total number of boosts needed to reach the next level; if absent, the next level isn't available. |
| premium_audience | flags.1?StatsPercentValue | Only returned to channel admins: contains the approximated number of Premium users subscribed to the channel, related to the total number of subscribers. |
| boost_url | string | Boost deep link » that can be used to boost the chat. |
| prepaid_giveaways | flags.3?Vector<PrepaidGiveaway> | A list of prepaid giveaways available for the chat; only returned to channel admins. |
| my_boost_slots | flags.2?Vector<int> | Indicates which of our boost slots we've assigned to this peer (populated if my_boost is set). |


## Type
premium.BoostsStatus

## Related pages
