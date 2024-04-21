# messages.receivedQueue
Confirms receipt of messages in a secret chat by client, cancels push notifications.
The method returns a list of random_ids of messages for which push notifications were cancelled.

```
---functions---
messages.receivedQueue#55a5bb66 max_qts:int = Vector<long>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| max_qts | int | Maximum qts value available at the client |


## Result
Vector<long>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | MAX_QTS_INVALID | The specified max_qts is invalid. |
| 500 | MSG_WAIT_FAILED | A waiting call returned an error. |

