# premium.getBoostsList
Obtains info about the boosts that were applied to a certain channel (admins only)

```
premium.boostsList#86f8613c flags:# count:int boosts:Vector<Boost> next_offset:flags.0?string users:Vector<User> = premium.BoostsList;
---functions---
premium.getBoostsList#60f67660 flags:# gifts:flags.0?true peer:InputPeer offset:string limit:int = premium.BoostsList;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| gifts | flags.0?true | Whether to return only info about boosts received from gift codes and giveaways created by the channel » |
| peer | InputPeer | The channel |
| offset | string | Offset for pagination, obtained from premium.boostsList.next_offset |
| limit | int | Maximum number of results to return, see pagination |


## Result
premium.BoostsList

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

