# payments.getConnectedStarRefBots
Fetch all affiliations we have created for a certain peer

```
payments.connectedStarRefBots#98d5ea1d count:int connected_bots:Vector<ConnectedBotStarRef> users:Vector<User> = payments.ConnectedStarRefBots;
---functions---
payments.getConnectedStarRefBots#5869a553 flags:# peer:InputPeer offset_date:flags.2?int offset_link:flags.2?string limit:int = payments.ConnectedStarRefBots;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | The affiliated peer |
| offset_date | flags.2?int | If set, returns only results older than the specified unixtime |
| offset_link | flags.2?string | Offset for pagination, taken from the last returned connectedBotStarRef.url (initially empty) |
| limit | int | Maximum number of results to return, see pagination |


## Result
payments.ConnectedStarRefBots

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

