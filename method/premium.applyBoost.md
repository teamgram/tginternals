# premium.applyBoost
Apply one or more boosts » to a peer.

```
premium.myBoosts#9ae228e2 my_boosts:Vector<MyBoost> chats:Vector<Chat> users:Vector<User> = premium.MyBoosts;
---functions---
premium.applyBoost#6b7da746 flags:# slots:flags.0?Vector<int> peer:InputPeer = premium.MyBoosts;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| slots | flags.0?Vector<int> | Which boost slots to assign to this peer. |
| peer | InputPeer | The peer to boost. |


## Result
premium.MyBoosts

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOOSTS_EMPTY | No boost slots were specified. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | SLOTS_EMPTY | The specified slot list is empty. |

