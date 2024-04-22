# InputReplyTo
Contains info about a message or story to reply to.

```
inputReplyToMessage#22c0f6d5 flags:# reply_to_msg_id:int top_msg_id:flags.0?int reply_to_peer_id:flags.1?InputPeer quote_text:flags.2?string quote_entities:flags.3?Vector<MessageEntity> quote_offset:flags.4?int = InputReplyTo;
inputReplyToStory#15b0f283 user_id:InputUser story_id:int = InputReplyTo;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| inputReplyToMessage | Reply to a message. |
| inputReplyToStory | Reply to a story. |


## Methods
| Method | Description |
| ---- | ----------- |


