# messages.getFactCheck
Fetch one or more factchecks, see here » for the full flow.

```
---functions---
messages.getFactCheck#b9cdc5ee peer:InputPeer msg_id:Vector<int> = Vector<FactCheck>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer where the messages were sent. |
| msg_id | Vector<int> | Messages that have associated factCheck constructors with the need_check flag set. |


## Result
Vector<FactCheck>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

