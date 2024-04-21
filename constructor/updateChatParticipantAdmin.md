# updateChatParticipantAdmin
Admin permissions of a user in a basic group were changed

```
updateChatParticipantAdmin#d7ca61a2 chat_id:long user_id:long is_admin:Bool version:int = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| chat_id | long | Chat ID |
| user_id | long | ID of the (de)admined user |
| is_admin | Bool | Whether the user was rendered admin |
| version | int | Used in basic groups to reorder updates and make sure that all of them was received. |


## Type
Update

## Related pages
