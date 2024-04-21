# invokeWithLayer
Invoke the specified query using the specified API layer

```
---functions---
invokeWithLayer#da9b0d0d {X:Type} layer:int query:!X = X;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| layer | int | The layer to use |
| query | !X | The query |


## Result
The type returned by the invoked method.

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | AUTH_BYTES_INVALID | The provided authorization is invalid. |
| 400 | CDN_METHOD_INVALID | You can't call this method in a CDN DC. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | CONNECTION_API_ID_INVALID | The provided API id is invalid. |
| 406 | INVITE_HASH_EXPIRED | The invite link has expired. |

