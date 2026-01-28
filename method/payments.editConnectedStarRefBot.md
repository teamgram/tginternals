# payments.editConnectedStarRefBot
Leave a bot's affiliate program »

```
payments.connectedStarRefBots#98d5ea1d count:int connected_bots:Vector<ConnectedBotStarRef> users:Vector<User> = payments.ConnectedStarRefBots;
---functions---
payments.editConnectedStarRefBot#e4fca4a3 flags:# revoked:flags.0?true peer:InputPeer link:string = payments.ConnectedStarRefBots;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| revoked | flags.0?true | If set, leaves the bot's affiliate program |
| peer | InputPeer | The peer that was affiliated |
| link | string | The affiliate link to revoke |


## Result
payments.ConnectedStarRefBots

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | STARREF_HASH_REVOKED | The specified affiliate link was already revoked. |

