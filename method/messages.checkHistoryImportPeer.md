# messages.checkHistoryImportPeer
Check whether chat history exported from another chat app can be imported into a specific Telegram chat, click here for more info ».

```
messages.checkedHistoryImportPeer#a24de717 confirm_text:string = messages.CheckedHistoryImportPeer;
---functions---
messages.checkHistoryImportPeer#5dc60f03 peer:InputPeer = messages.CheckedHistoryImportPeer;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The chat where we want to import history ». |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | USER_NOT_MUTUAL_CONTACT | The provided user is not a mutual contact. |

