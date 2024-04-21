# channels.getForumTopics
Get topics of a forum

```
messages.forumTopics#367617d3 flags:# order_by_create_date:flags.0?true count:int topics:Vector<ForumTopic> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> pts:int = messages.ForumTopics;
---functions---
channels.getForumTopics#de560d1 flags:# channel:InputChannel q:flags.0?string offset_date:int offset_id:int offset_topic:int limit:int = messages.ForumTopics;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| channel | InputChannel | Supergroup |
| q | flags.0?string | Search query |
| offset_date | int | Offsets for pagination, for more info click here, date of the last message of the last found topic. Use 0 or any date in the future to get results from the last topic. |
| offset_id | int | Offsets for pagination, for more info click here, ID of the last message of the last found topic (or initially 0). |
| offset_topic | int | Offsets for pagination, for more info click here, ID of the last found topic (or initially 0). |
| limit | int | Maximum number of results to return, see pagination. For optimal performance, the number of returned topics is chosen by the server and can be smaller than the specified limit. |


## Result
messages.ForumTopics

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_FORUM_MISSING | This supergroup is not a forum. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |

