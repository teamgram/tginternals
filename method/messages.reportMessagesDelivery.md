# messages.reportMessagesDelivery
Used for Telegram Gateway verification messages »: indicate to the server that one or more messages were received by the client, if requested by the message.report_delivery_until_date flag or the equivalent flag in push notifications.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.reportMessagesDelivery#5a6d7395 flags:# push:flags.0?true peer:InputPeer id:Vector<int> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| push | flags.0?true | Must be set if the messages were received from a push notification. |
| peer | InputPeer | The peer where the messages were received. |
| id | Vector<int> | The IDs of the received messages. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

