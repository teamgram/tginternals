# Payments.ConnectedStarRefBots
Active affiliations

```
payments.connectedStarRefBots#98d5ea1d count:int connected_bots:Vector<ConnectedBotStarRef> users:Vector<User> = payments.ConnectedStarRefBots;

---functions---

payments.getConnectedStarRefBots#5869a553 flags:# peer:InputPeer offset_date:flags.2?int offset_link:flags.2?string limit:int = payments.ConnectedStarRefBots;
payments.getConnectedStarRefBot#b7d998f0 peer:InputPeer bot:InputUser = payments.ConnectedStarRefBots;
payments.connectStarRefBot#7ed5348a peer:InputPeer bot:InputUser = payments.ConnectedStarRefBots;
payments.editConnectedStarRefBot#e4fca4a3 flags:# revoked:flags.0?true peer:InputPeer link:string = payments.ConnectedStarRefBots;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| payments.connectedStarRefBots | Active affiliations |


## Methods
| Method | Description |
| ---- | ----------- |
| payments.getConnectedStarRefBots | Fetch all affiliations we have created for a certain peer |
| payments.getConnectedStarRefBot | Fetch info about a specific bot affiliation » |
| payments.connectStarRefBot | Join a bot's affiliate program, becoming an affiliate » |
| payments.editConnectedStarRefBot | Leave a bot's affiliate program » |


