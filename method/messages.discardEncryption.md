# messages.discardEncryption
Cancels a request for creation and/or delete info on secret chat.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.discardEncryption#f393aea0 flags:# delete_history:flags.0?true chat_id:int = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| delete_history | flags.0?true | Whether to delete the entire chat history for the other user as well |
| chat_id | int | Secret chat ID |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ID_EMPTY | The provided chat ID is empty. |
| 400 | ENCRYPTION_ALREADY_ACCEPTED | Secret chat already accepted. |
| 400 | ENCRYPTION_ALREADY_DECLINED | The secret chat was already declined. |
| 400 | ENCRYPTION_ID_INVALID | The provided secret chat ID is invalid. |

