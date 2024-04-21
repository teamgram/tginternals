# stories.boostsStatus
The current boost status » of a channel.

```
Constructor schema is available as of layer 165. Switch »
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| my_boost | flags.2?true | Whether we're currently boosting this channel. |
| level | int | The current boost level of the channel. |
| current_level_boosts | int | The number of boosts acquired so far in the current level. |
| boosts | int | Total number of boosts acquired so far. |
| next_level_boosts | flags.0?int | Total number of boosts needed to reach the next level; if absent, the next level isn't available. |
| premium_audience | flags.1?StatsPercentValue | Only returned to channel admins: contains the approximated number of Premium users subscribed to the channel, related to the total number of subscribers. |


## Type
 

## Related pages
