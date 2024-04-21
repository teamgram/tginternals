# updates.getDifference
Get new updates.

```
updates.differenceEmpty#5d75a138 date:int seq:int = updates.Difference;
updates.difference#f49ca0 new_messages:Vector<Message> new_encrypted_messages:Vector<EncryptedMessage> other_updates:Vector<Update> chats:Vector<Chat> users:Vector<User> state:updates.State = updates.Difference;
updates.differenceSlice#a8fb1981 new_messages:Vector<Message> new_encrypted_messages:Vector<EncryptedMessage> other_updates:Vector<Update> chats:Vector<Chat> users:Vector<User> intermediate_state:updates.State = updates.Difference;
updates.differenceTooLong#4afe8f6d pts:int = updates.Difference;
---functions---
updates.getDifference#19c2f763 flags:# pts:int pts_limit:flags.1?int pts_total_limit:flags.0?int date:int qts:int qts_limit:flags.2?int = updates.Difference;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| pts | int | PTS, see updates. |
| pts_limit | flags.1?int | PTS limit |
| pts_total_limit | flags.0?int | For fast updating: if provided and pts + pts_total_limit < remote pts, updates.differenceTooLong will be returned.Simply tells the server to not return the difference if it is bigger than pts_total_limitIf the remote pts is too big (> ~4000000), this field will default to 1000000 |
| date | int | date, see updates. |
| qts | int | QTS, see updates. |
| qts_limit | flags.2?int | QTS limit |


## Result
updates.Difference

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CDN_METHOD_INVALID | You can't call this method in a CDN DC. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | DATE_EMPTY | Date empty. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PERSISTENT_TIMESTAMP_EMPTY | Persistent timestamp empty. |
| 400 | PERSISTENT_TIMESTAMP_INVALID | Persistent timestamp invalid. |
| 500 | RANDOM_ID_DUPLICATE | You provided a random ID that was already used. |
| 400 | USERNAME_INVALID | The provided username is not valid. |
| 400 | USER_NOT_PARTICIPANT | You're not a member of this supergroup/channel. |

