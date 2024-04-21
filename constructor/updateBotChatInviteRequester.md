# updateBotChatInviteRequester
Someone has requested to join a chat or channel (bots only, users will receive an updatePendingJoinRequests, instead)

```
updateBotChatInviteRequester#11dfa986 peer:Peer date:int user_id:long about:string invite:ExportedChatInvite qts:int = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | Peer | The chat or channel in question |
| date | int | When was the join request » made |
| user_id | long | The user ID that is asking to join the chat or channel |
| about | string | Bio of the user |
| invite | ExportedChatInvite | Chat invite link that was used by the user to send the join request » |
| qts | int | QTS event sequence identifier |


## Type
Update

## Related pages
