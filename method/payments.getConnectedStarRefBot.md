# payments.getConnectedStarRefBot
Fetch info about a specific bot affiliation »

```
payments.connectedStarRefBots#98d5ea1d count:int connected_bots:Vector<ConnectedBotStarRef> users:Vector<User> = payments.ConnectedStarRefBots;
---functions---
payments.getConnectedStarRefBot#b7d998f0 peer:InputPeer bot:InputUser = payments.ConnectedStarRefBots;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The affiliated peer |
| bot | InputUser | The bot that offers the affiliate program |


## Result
payments.ConnectedStarRefBots

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

