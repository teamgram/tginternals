# messages.startHistoryImport
Complete the history import process, importing all messages into the chat.
To be called only after initializing the import with messages.initHistoryImport and uploading all files using messages.uploadImportedMedia.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.startHistoryImport#b43df344 peer:InputPeer import_id:long = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The Telegram chat where the messages should be imported, click here for more info » |
| import_id | long | Identifier of a history import session, returned by messages.initHistoryImport. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | IMPORT_ID_INVALID | The specified import ID is invalid. |

