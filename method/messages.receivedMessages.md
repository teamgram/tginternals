# messages.receivedMessages
Confirms receipt of messages by a client, cancels PUSH-notification sending.

```
---functions---
messages.receivedMessages#5a954c0 max_id:int = Vector<ReceivedNotifyMessage>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| max_id | int | Maximum message ID available in a client. |


## Result
Vector<ReceivedNotifyMessage>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

