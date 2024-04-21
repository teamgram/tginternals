# updateBotMessageReaction
Bots only: a user has changed their reactions on a message with public reactions.

```
updateBotMessageReaction#ac21d3ce peer:Peer msg_id:int date:int actor:Peer old_reactions:Vector<Reaction> new_reactions:Vector<Reaction> qts:int = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | Peer | Peer of the reacted-to message. |
| msg_id | int | ID of the reacted-to message. |
| date | int | Date of the change. |
| actor | Peer | The user that (un)reacted to the message. |
| old_reactions | Vector<Reaction> | Old reactions |
| new_reactions | Vector<Reaction> | New reactions |
| qts | int | QTS event sequence identifier |


## Type
Update

## Related pages
