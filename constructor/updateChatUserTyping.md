# updateChatUserTyping
The user is preparing a message in a group; typing, recording, uploading, etc. This update is valid for 6 seconds. If no further updates of this kind are received after 6 seconds, it should be considered that the user stopped doing whatever they were doing

```
updateChatUserTyping#83487af0 chat_id:long from_id:Peer action:SendMessageAction = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| chat_id | long | Group id |
| from_id | Peer | Peer that started typing (can be the chat itself, in case of anonymous admins). |
| action | SendMessageAction | Type of action |


## Type
Update

## Related pages
