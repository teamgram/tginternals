# updateBotMessageReactions
Bots only: the number of reactions on a message with anonymous reactions has changed.

```
updateBotMessageReactions#9cb7759 peer:Peer msg_id:int date:int reactions:Vector<ReactionCount> qts:int = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | Peer | Peer of the reacted-to message. |
| msg_id | int | ID of the reacted-to message. |
| date | int | Date of the change. |
| reactions | Vector<ReactionCount> | New reaction counters. |
| qts | int | QTS event sequence identifier |


## Type
Update

## Related pages
