# channels.getForumTopicsByID
Get forum topics by their ID

```
messages.forumTopics#367617d3 flags:# order_by_create_date:flags.0?true count:int topics:Vector<ForumTopic> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> pts:int = messages.ForumTopics;
---functions---
channels.getForumTopicsByID#b0831eb9 channel:InputChannel topics:Vector<int> = messages.ForumTopics;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | Forum |
| topics | Vector<int> | Topic IDs |


## Result
messages.ForumTopics

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_FORUM_MISSING | This supergroup is not a forum. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | TOPICS_EMPTY | You specified no topic IDs. |

