# channels.getMessages
Get channel/supergroup messages

```
messages.messages#8c718e87 messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesSlice#762b263d flags:# inexact:flags.1?true count:int next_rate:flags.0?int offset_id_offset:flags.2?int search_flood:flags.3?SearchPostsFlood messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.channelMessages#c776ba4e flags:# inexact:flags.1?true pts:int count:int offset_id_offset:flags.2?int messages:Vector<Message> topics:Vector<ForumTopic> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesNotModified#74535f21 count:int = messages.Messages;
---functions---
channels.getMessages#ad8c9a23 channel:InputChannel id:Vector<InputMessage> = messages.Messages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | Channel/supergroup |
| id | Vector<InputMessage> | IDs of messages to get |


## Result
messages.Messages

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 406 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_NOT_MODIFIED | No changes were made to chat information because the new information you passed is identical to the current information. |
| 400 | FROZEN_PARTICIPANT_MISSING | The current account is frozen, and cannot access the specified peer. |
| 400 | MESSAGE_IDS_EMPTY | No message ids were provided. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | USER_BANNED_IN_CHANNEL | You're banned from sending messages in supergroups/channels. |

