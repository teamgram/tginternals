# invokeAfterMsg
Invokes a query after successful completion of one of the previous queries.

```
---functions---
invokeAfterMsg#cb9f372d {X:Type} msg_id:long query:!X = X;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| msg_id | long | Message identifier on which a current query depends |
| query | !X | The query itself |


## Result
The type returned by the invoked method.

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

