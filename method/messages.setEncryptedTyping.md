# messages.setEncryptedTyping
Send typing event by the current user to a secret chat.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.setEncryptedTyping#791451ed peer:InputEncryptedChat typing:Bool = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputEncryptedChat | Secret chat ID |
| typing | Bool | Typing.Possible values:(boolTrue), if the user started typing and more than 5 seconds have passed since the last request(boolFalse), if the user stopped typing |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |

