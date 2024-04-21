# chatlists.getLeaveChatlistSuggestions
Returns identifiers of pinned or always included chats from a chat folder imported using a chat folder deep link », which are suggested to be left when the chat folder is deleted.

```
---functions---
chatlists.getLeaveChatlistSuggestions#fdbcd714 chatlist:InputChatlist = Vector<Peer>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| chatlist | InputChatlist | Folder ID |


## Result
Vector<Peer>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | FILTER_ID_INVALID | The specified filter ID is invalid. |
| 400 | FILTER_NOT_SUPPORTED | The specified filter cannot be used in this context. |

