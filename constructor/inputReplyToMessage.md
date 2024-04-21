# inputReplyToMessage
Reply to a message.

```
inputReplyToMessage#22c0f6d5 flags:# reply_to_msg_id:int top_msg_id:flags.0?int reply_to_peer_id:flags.1?InputPeer quote_text:flags.2?string quote_entities:flags.3?Vector<MessageEntity> quote_offset:flags.4?int = InputReplyTo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| reply_to_msg_id | int | The message ID to reply to. |
| top_msg_id | flags.0?int | This field must contain the topic ID only when replying to messages in forum topics different from the "General" topic (i.e. reply_to_msg_id is set and reply_to_msg_id != topicID and topicID != 1).  If the replied-to message is deleted before the method finishes execution, the value in this field will be used to send the message to the correct topic, instead of the "General" topic. |
| reply_to_peer_id | flags.1?InputPeer | Used to reply to messages sent to another chat (specified here), can only be used for non-protected chats and messages. |
| quote_text | flags.2?string | Used to quote-reply to only a certain section (specified here) of the original message. The maximum UTF-8 length for quotes is specified in the quote_length_max config key. |
| quote_entities | flags.3?Vector<MessageEntity> | Message entities for styled text from the quote_text field. |
| quote_offset | flags.4?int | Offset of the message quote_text within the original message (in UTF-16 code units). |


## Type
InputReplyTo

## Related pages
