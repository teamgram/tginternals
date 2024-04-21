# messageReplyHeader
Message replies and thread information

```
messageReplyHeader#afbc09db flags:# reply_to_scheduled:flags.2?true forum_topic:flags.3?true quote:flags.9?true reply_to_msg_id:flags.4?int reply_to_peer_id:flags.0?Peer reply_from:flags.5?MessageFwdHeader reply_media:flags.8?MessageMedia reply_to_top_id:flags.1?int quote_text:flags.6?string quote_entities:flags.7?Vector<MessageEntity> quote_offset:flags.10?int = MessageReplyHeader;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| reply_to_scheduled | flags.2?true | This is a reply to a scheduled message. |
| forum_topic | flags.3?true | Whether this message was sent in a forum topic (except for the General topic). |
| quote | flags.9?true | Whether this message is quoting a part of another message. |
| reply_to_msg_id | flags.4?int | ID of message to which this message is replying |
| reply_to_peer_id | flags.0?Peer | For replies sent in channel discussion threads of which the current user is not a member, the discussion group ID |
| reply_from | flags.5?MessageFwdHeader | When replying to a message sent by a certain peer to another chat, contains info about the peer that originally sent the message to that other chat. |
| reply_media | flags.8?MessageMedia | When replying to a media sent by a certain peer to another chat, contains the media of the replied-to message. |
| reply_to_top_id | flags.1?int | ID of the message that started this message thread |
| quote_text | flags.6?string | Used to quote-reply to only a certain section (specified here) of the original message. |
| quote_entities | flags.7?Vector<MessageEntity> | Message entities for styled text from the quote_text field. |
| quote_offset | flags.10?int | Offset of the message quote_text within the original message (in UTF-16 code units). |


## Type
MessageReplyHeader

## Related pages
