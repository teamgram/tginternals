# updates.Difference
Occurred changes.

```
updates.differenceEmpty#5d75a138 date:int seq:int = updates.Difference;
updates.difference#f49ca0 new_messages:Vector<Message> new_encrypted_messages:Vector<EncryptedMessage> other_updates:Vector<Update> chats:Vector<Chat> users:Vector<User> state:updates.State = updates.Difference;
updates.differenceSlice#a8fb1981 new_messages:Vector<Message> new_encrypted_messages:Vector<EncryptedMessage> other_updates:Vector<Update> chats:Vector<Chat> users:Vector<User> intermediate_state:updates.State = updates.Difference;
updates.differenceTooLong#4afe8f6d pts:int = updates.Difference;

---functions---

updates.getDifference#19c2f763 flags:# pts:int pts_limit:flags.1?int pts_total_limit:flags.0?int date:int qts:int qts_limit:flags.2?int = updates.Difference;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| updates.differenceEmpty | No events. |
| updates.difference | Full list of occurred events. |
| updates.differenceSlice | Incomplete list of occurred events. |
| updates.differenceTooLong | The difference is too long, and the specified state must be used to refetch updates. |


## Methods
| Method | Description |
| ---- | ----------- |
| updates.getDifference | Get new updates. |


