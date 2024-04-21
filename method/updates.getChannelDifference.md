# updates.getChannelDifference
Returns the difference between the current state of updates of a certain channel and transmitted.

```
updates.channelDifferenceEmpty#3e11affb flags:# final:flags.0?true pts:int timeout:flags.1?int = updates.ChannelDifference;
updates.channelDifferenceTooLong#a4bcc6fe flags:# final:flags.0?true timeout:flags.1?int dialog:Dialog messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = updates.ChannelDifference;
updates.channelDifference#2064674e flags:# final:flags.0?true pts:int timeout:flags.1?int new_messages:Vector<Message> other_updates:Vector<Update> chats:Vector<Chat> users:Vector<User> = updates.ChannelDifference;
---functions---
updates.getChannelDifference#3173d78 flags:# force:flags.0?true channel:InputChannel filter:ChannelMessagesFilter pts:int limit:int = updates.ChannelDifference;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| force | flags.0?true | Set to true to skip some possibly unneeded updates and reduce server-side load |
| channel | InputChannel | The channel |
| filter | ChannelMessagesFilter | Messsage filter |
| pts | int | Persistent timestamp (see updates) |
| limit | int | How many updates to fetch, max 100000Ordinary (non-bot) users are supposed to pass 10-100 |


## Result
updates.ChannelDifference

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 406 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 403 | CHANNEL_PUBLIC_GROUP_NA | channel/supergroup not available. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | FROM_MESSAGE_BOT_DISABLED | Bots can't use fromMessage min constructors. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PERSISTENT_TIMESTAMP_EMPTY | Persistent timestamp empty. |
| 400 | PERSISTENT_TIMESTAMP_INVALID | Persistent timestamp invalid. |
| 500 | PERSISTENT_TIMESTAMP_OUTDATED | Channel internal replication issues, try again later (treat this like an RPC_CALL_FAIL). |
| 400 | PINNED_DIALOGS_TOO_MUCH | Too many pinned dialogs. |
| 400 | RANGES_INVALID | Invalid range provided. |
| 400 | USER_BANNED_IN_CHANNEL | You're banned from sending messages in supergroups/channels. |

