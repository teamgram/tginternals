# channels.searchPosts
Globally search for posts from public channels » (including those we aren't a member of) containing either a specific hashtag, or a full text query.

```
messages.messages#8c718e87 messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesSlice#762b263d flags:# inexact:flags.1?true count:int next_rate:flags.0?int offset_id_offset:flags.2?int search_flood:flags.3?SearchPostsFlood messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.channelMessages#c776ba4e flags:# inexact:flags.1?true pts:int count:int offset_id_offset:flags.2?int messages:Vector<Message> topics:Vector<ForumTopic> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesNotModified#74535f21 count:int = messages.Messages;
---functions---
channels.searchPosts#f2c4f24d flags:# hashtag:flags.0?string query:flags.1?string offset_rate:int offset_peer:InputPeer offset_id:int limit:int allow_paid_stars:flags.2?long = messages.Messages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| hashtag | flags.0?string | The hashtag to search, without the # character. |
| query | flags.1?string | The full text query: each user has a limited amount of free full text search slots, after which payment is required, see here » for more info on the full flow. |
| offset_rate | int | Initially 0, then set to the next_rate parameter of messages.messagesSlice, or if that is absent, the date of the last returned message. |
| offset_peer | InputPeer | Offsets for pagination, for more info click here |
| offset_id | int | Offsets for pagination, for more info click here |
| limit | int | Maximum number of results to return, see pagination |
| allow_paid_stars | flags.2?long | For full text post searches (query), allows payment of the specified amount of Stars for the search, see here » for more info on the full flow. |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 420 | FROZEN_METHOD_INVALID | The current account is frozen, and thus cannot execute the specified action. |

