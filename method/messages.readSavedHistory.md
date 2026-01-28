# messages.readSavedHistory
Mark messages as read in a monoforum topic ».

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.readSavedHistory#ba4a3b5b parent_peer:InputPeer peer:InputPeer max_id:int = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| parent_peer | InputPeer | ID of the monoforum group. |
| peer | InputPeer | ID of the topic. |
| max_id | int | If a positive value is passed, only messages with identifiers less or equal than the given one will be read. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | PARENT_PEER_INVALID | The specified parent_peer is invalid. |

