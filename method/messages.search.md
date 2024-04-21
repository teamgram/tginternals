# messages.search
Search for messages.

```
messages.messages#8c718e87 messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesSlice#3a54685e flags:# inexact:flags.1?true count:int next_rate:flags.0?int offset_id_offset:flags.2?int messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.channelMessages#c776ba4e flags:# inexact:flags.1?true pts:int count:int offset_id_offset:flags.2?int messages:Vector<Message> topics:Vector<ForumTopic> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesNotModified#74535f21 count:int = messages.Messages;
---functions---
messages.search#a7b4e929 flags:# peer:InputPeer q:string from_id:flags.0?InputPeer saved_peer_id:flags.2?InputPeer top_msg_id:flags.1?int filter:MessagesFilter min_date:int max_date:int offset_id:int add_offset:int limit:int max_id:int min_id:int hash:long = messages.Messages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | User or chat, histories with which are searched, or (inputPeerEmpty) constructor to search in all private chats and normal groups (not channels) ». Use messages.searchGlobal to search globally in all chats, groups, supergroups and channels. |
| q | string | Text search request |
| from_id | flags.0?InputPeer | Only return messages sent by the specified user ID |
| saved_peer_id | flags.2?InputPeer | Search within the saved message dialog » with this ID. |
| top_msg_id | flags.1?int | Thread ID |
| filter | MessagesFilter | Filter to return only specified message types |
| min_date | int | If a positive value was transferred, only messages with a sending date bigger than the transferred one will be returned |
| max_date | int | If a positive value was transferred, only messages with a sending date smaller than the transferred one will be returned |
| offset_id | int | Only return messages starting from the specified message ID |
| add_offset | int | Additional offset |
| limit | int | Number of results to return |
| max_id | int | Maximum message ID to return |
| min_id | int | Minimum message ID to return |
| hash | long | Hash |


## Result
messages.Messages

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 403 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | FROM_PEER_INVALID | The specified from_id is invalid. |
| 400 | INPUT_FILTER_INVALID | The specified filter is invalid. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | PEER_ID_NOT_SUPPORTED | The provided peer ID is not supported. |
| 400 | SEARCH_QUERY_EMPTY | The search query is empty. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

