# messages.saveDraft
Save a message draft associated to a chat.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.saveDraft#54ae308e flags:# no_webpage:flags.1?true invert_media:flags.6?true reply_to:flags.4?InputReplyTo peer:InputPeer message:string entities:flags.3?Vector<MessageEntity> media:flags.5?InputMedia effect:flags.7?long suggested_post:flags.8?SuggestedPost = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| no_webpage | flags.1?true | Disable generation of the webpage preview |
| invert_media | flags.6?true | If set, any eventual webpage preview will be shown on top of the message instead of at the bottom. |
| reply_to | flags.4?InputReplyTo | If set, indicates that the message should be sent in reply to the specified message or story. |
| peer | InputPeer | Destination of the message that should be sent |
| message | string | The draft |
| entities | flags.3?Vector<MessageEntity> | Message entities for styled text |
| media | flags.5?InputMedia | Attached media |
| effect | flags.7?long | Specifies a message effect » to use for the message. |
| suggested_post | flags.8?SuggestedPost | Used to suggest a post to a channel, see here » for more info on the full flow. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | ENTITY_BOUNDS_INVALID | A specified entity offset or length is invalid, see here » for info on how to properly compute the entity offset/length. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

