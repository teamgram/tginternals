# draftMessage
Represents a message draft.

```
draftMessage#96eaa5eb flags:# no_webpage:flags.1?true invert_media:flags.6?true reply_to:flags.4?InputReplyTo message:string entities:flags.3?Vector<MessageEntity> media:flags.5?InputMedia date:int effect:flags.7?long suggested_post:flags.8?SuggestedPost = DraftMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| no_webpage | flags.1?true | Whether no webpage preview will be generated |
| invert_media | flags.6?true | If set, any eventual webpage preview will be shown on top of the message instead of at the bottom. |
| reply_to | flags.4?InputReplyTo | If set, indicates that the message should be sent in reply to the specified message or story. |
| message | string | The draft |
| entities | flags.3?Vector<MessageEntity> | Message entities for styled text. |
| media | flags.5?InputMedia | Media. |
| date | int | Date of last update of the draft. |
| effect | flags.7?long | A message effect that should be played as specified here ». |
| suggested_post | flags.8?SuggestedPost | Used to suggest a post to a channel, see here » for more info on the full flow. |


## Type
DraftMessage

## Related pages
