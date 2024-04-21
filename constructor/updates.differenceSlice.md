# updates.differenceSlice
Incomplete list of occurred events.

```
updates.differenceSlice#a8fb1981 new_messages:Vector<Message> new_encrypted_messages:Vector<EncryptedMessage> other_updates:Vector<Update> chats:Vector<Chat> users:Vector<User> intermediate_state:updates.State = updates.Difference;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| new_messages | Vector<Message> | List of new messages |
| new_encrypted_messages | Vector<EncryptedMessage> | New messages from the encrypted event sequence |
| other_updates | Vector<Update> | List of updates |
| chats | Vector<Chat> | List of chats mentioned in events |
| users | Vector<User> | List of users mentioned in events |
| intermediate_state | updates.State | Intermediary state |


## Type
updates.Difference

## Related pages
