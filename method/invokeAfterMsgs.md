# invokeAfterMsgs
Invokes a query after a successful completion of previous queries

```
---functions---
invokeAfterMsgs#3dc4b4f0 {X:Type} msg_ids:Vector<long> query:!X = X;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| msg_ids | Vector<long> | List of messages on which a current query depends |
| query | !X | The query itself |


## Result
The type returned by the invoked method.

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

