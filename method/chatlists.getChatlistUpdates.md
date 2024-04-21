# chatlists.getChatlistUpdates
Fetch new chats associated with an imported chat folder deep link ». Must be invoked at most every chatlist_update_period seconds (as per the related client configuration parameter »).

```
chatlists.chatlistUpdates#93bd878d missing_peers:Vector<Peer> chats:Vector<Chat> users:Vector<User> = chatlists.ChatlistUpdates;
---functions---
chatlists.getChatlistUpdates#89419521 chatlist:InputChatlist = chatlists.ChatlistUpdates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| chatlist | InputChatlist | The folder |


## Result
chatlists.ChatlistUpdates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | FILTER_ID_INVALID | The specified filter ID is invalid. |
| 400 | FILTER_NOT_SUPPORTED | The specified filter cannot be used in this context. |
| 400 | INPUT_CHATLIST_INVALID | The specified folder is invalid. |

