# messages.DiscussionMessage
Info about a message thread

```
messages.discussionMessage#a6341782 flags:# messages:Vector<Message> max_id:flags.0?int read_inbox_max_id:flags.1?int read_outbox_max_id:flags.2?int unread_count:int chats:Vector<Chat> users:Vector<User> = messages.DiscussionMessage;

---functions---

messages.getDiscussionMessage#446972fd peer:InputPeer msg_id:int = messages.DiscussionMessage;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.discussionMessage | Information about a message thread |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.getDiscussionMessage | Get discussion message from the associated discussion group of a channel to show it on top of the comment section, without actually joining the group |


