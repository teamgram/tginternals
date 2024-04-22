# Premium.BoostsStatus
Contains info about the current boost status of a peer.

```
premium.boostsStatus#4959427a flags:# my_boost:flags.2?true level:int current_level_boosts:int boosts:int gift_boosts:flags.4?int next_level_boosts:flags.0?int premium_audience:flags.1?StatsPercentValue boost_url:string prepaid_giveaways:flags.3?Vector<PrepaidGiveaway> my_boost_slots:flags.2?Vector<int> = premium.BoostsStatus;

---functions---

premium.getBoostsStatus#42f1f61 peer:InputPeer = premium.BoostsStatus;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| premium.boostsStatus | Contains info about the current boost status of a peer. |


## Methods
| Method | Description |
| ---- | ----------- |
| premium.getBoostsStatus | Gets the current number of boosts of a channel. |


