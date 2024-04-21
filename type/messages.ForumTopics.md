# messages.ForumTopics
Contains information about multiple forum topics

```
messages.forumTopics#367617d3 flags:# order_by_create_date:flags.0?true count:int topics:Vector<ForumTopic> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> pts:int = messages.ForumTopics;

---functions---

channels.getForumTopics#de560d1 flags:# channel:InputChannel q:flags.0?string offset_date:int offset_id:int offset_topic:int limit:int = messages.ForumTopics;
channels.getForumTopicsByID#b0831eb9 channel:InputChannel topics:Vector<int> = messages.ForumTopics;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.forumTopics | Contains information about multiple forum topics |


## Methods
| Method | Description |
| ---- | ----------- |
| channels.getForumTopics | Get topics of a forum |
| channels.getForumTopicsByID | Get forum topics by their ID |


