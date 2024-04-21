# premium.getUserBoosts
Returns the lists of boost that were applied to a channel by a specific user (admins only)

```
premium.boostsList#86f8613c flags:# count:int boosts:Vector<Boost> next_offset:flags.0?string users:Vector<User> = premium.BoostsList;
---functions---
premium.getUserBoosts#39854d1f peer:InputPeer user_id:InputUser = premium.BoostsList;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The channel |
| user_id | InputUser | The user |


## Result
premium.BoostsList

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

