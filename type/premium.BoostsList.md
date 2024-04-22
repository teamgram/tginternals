# Premium.BoostsList
List of boosts that were applied to a peer by multiple users.

```
premium.boostsList#86f8613c flags:# count:int boosts:Vector<Boost> next_offset:flags.0?string users:Vector<User> = premium.BoostsList;

---functions---

premium.getBoostsList#60f67660 flags:# gifts:flags.0?true peer:InputPeer offset:string limit:int = premium.BoostsList;
premium.getUserBoosts#39854d1f peer:InputPeer user_id:InputUser = premium.BoostsList;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| premium.boostsList | List of boosts that were applied to a peer by multiple users. |


## Methods
| Method | Description |
| ---- | ----------- |
| premium.getBoostsList | Obtains info about the boosts that were applied to a certain channel (admins only) |
| premium.getUserBoosts | Returns the lists of boost that were applied to a channel by a specific user (admins only) |


