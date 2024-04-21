# messageReplies
Info about the comment section of a channel post, or a simple message thread

```
messageReplies#83d60fc2 flags:# comments:flags.0?true replies:int replies_pts:int recent_repliers:flags.1?Vector<Peer> channel_id:flags.0?long max_id:flags.2?int read_max_id:flags.3?int = MessageReplies;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| comments | flags.0?true | Whether this constructor contains information about the comment section of a channel post, or a simple message thread |
| replies | int | Contains the total number of replies in this thread or comment section. |
| replies_pts | int | PTS of the message that started this thread. |
| recent_repliers | flags.1?Vector<Peer> | For channel post comments, contains information about the last few comment posters for a specific thread, to show a small list of commenter profile pictures in client previews. |
| channel_id | flags.0?long | For channel post comments, contains the ID of the associated discussion supergroup |
| max_id | flags.2?int | ID of the latest message in this thread or comment section. |
| read_max_id | flags.3?int | Contains the ID of the latest read message in this thread or comment section. |


## Type
MessageReplies

## Related pages
