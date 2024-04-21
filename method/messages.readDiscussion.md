# messages.readDiscussion
Mark a thread as read

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.readDiscussion#f731a9f4 peer:InputPeer msg_id:int read_max_id:int = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Group ID |
| msg_id | int | ID of message that started the thread |
| read_max_id | int | ID up to which thread messages were read |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

