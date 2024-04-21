# messages.initHistoryImport
Import chat history from a foreign chat app into a specific Telegram chat, click here for more info about imported chats ».

```
messages.historyImport#1662af0b id:long = messages.HistoryImport;
---functions---
messages.initHistoryImport#34090c3b peer:InputPeer file:InputFile media_count:int = messages.HistoryImport;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The Telegram chat where the history should be imported. |
| file | InputFile | File with messages to import. |
| media_count | int | Number of media files associated with the chat that will be uploaded using messages.uploadImportedMedia. |


## Result
messages.HistoryImport

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | IMPORT_FILE_INVALID | The specified chat export file is invalid. |
| 400 | IMPORT_FORMAT_UNRECOGNIZED | The specified chat export file was exported from an unsupported chat app. |
| 406 | PREVIOUS_CHAT_IMPORT_ACTIVE_WAIT_%dMIN | Import for this chat is already in progress, wait %d minutes before starting a new one. |

