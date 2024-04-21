# messages.forumTopics
Contains information about multiple forum topics

```
messages.forumTopics#367617d3 flags:# order_by_create_date:flags.0?true count:int topics:Vector<ForumTopic> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> pts:int = messages.ForumTopics;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| order_by_create_date | flags.0?true | Whether the returned topics are ordered by creation date; if set, pagination by offset_date should use forumTopic.date; otherwise topics are ordered by the last message date, so paginate by the date of the message referenced by forumTopic.top_message. |
| count | int | Total number of topics matching query; may be more than the topics contained in topics, in which case pagination is required. |
| topics | Vector<ForumTopic> | Forum topics |
| messages | Vector<Message> | Related messages (contains the messages mentioned by forumTopic.top_message). |
| chats | Vector<Chat> | Related chats |
| users | Vector<User> | Related users |
| pts | int | Event count after generation |


## Type
messages.ForumTopics

## Related pages
