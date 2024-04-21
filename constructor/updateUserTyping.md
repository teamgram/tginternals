# updateUserTyping
The user is preparing a message; typing, recording, uploading, etc. This update is valid for 6 seconds. If no further updates of this kind are received after 6 seconds, it should be considered that the user stopped doing whatever they were doing

```
updateUserTyping#c01e857f user_id:long action:SendMessageAction = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| user_id | long | User id |
| action | SendMessageAction | Action type |


## Type
Update

## Related pages
