# draftMessage
Represents a message draft.

```
draftMessage#3fccf7ef flags:# no_webpage:flags.1?true invert_media:flags.6?true reply_to:flags.4?InputReplyTo message:string entities:flags.3?Vector<MessageEntity> media:flags.5?InputMedia date:int = DraftMessage;
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


## Type
DraftMessage

## Related pages
