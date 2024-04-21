# messages.readEncryptedHistory
Marks message history within a secret chat as read.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.readEncryptedHistory#7f4b690a peer:InputEncryptedChat max_date:int = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputEncryptedChat | Secret chat ID |
| max_date | int | Maximum date value for received messages in history |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | MAX_DATE_INVALID | The specified maximum date is invalid. |
| 400 | MSG_WAIT_FAILED | A waiting call returned an error. |

