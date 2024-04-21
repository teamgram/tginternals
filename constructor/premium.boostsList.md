# premium.boostsList
List of boosts that were applied to a peer by multiple users.

```
premium.boostsList#86f8613c flags:# count:int boosts:Vector<Boost> next_offset:flags.0?string users:Vector<User> = premium.BoostsList;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| count | int | Total number of results |
| boosts | Vector<Boost> | Boosts |
| next_offset | flags.0?string | Offset that can be used for pagination. |
| users | Vector<User> | Mentioned users |


## Type
premium.BoostsList

## Related pages
