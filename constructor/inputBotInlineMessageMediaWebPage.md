# inputBotInlineMessageMediaWebPage
Specifies options that will be used to generate the link preview for the message, or even a standalone link preview without an attached message.

```
inputBotInlineMessageMediaWebPage#bddcc510 flags:# invert_media:flags.3?true force_large_media:flags.4?true force_small_media:flags.5?true optional:flags.6?true message:string entities:flags.1?Vector<MessageEntity> url:string reply_markup:flags.2?ReplyMarkup = InputBotInlineMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| invert_media | flags.3?true | If set, any eventual webpage preview will be shown on top of the message instead of at the bottom. |
| force_large_media | flags.4?true | If set, specifies that a large media preview should be used. |
| force_small_media | flags.5?true | If set, specifies that a small media preview should be used. |
| optional | flags.6?true | If not set, a WEBPAGE_NOT_FOUND RPC error will be emitted if a webpage preview cannot be generated for the specified url; otherwise, no error will be emitted (unless the provided message is also empty, in which case a MESSAGE_EMPTY will be emitted, instead). |
| message | string | The message, can be empty. |
| entities | flags.1?Vector<MessageEntity> | Message entities for styled text |
| url | string | The URL to use for the link preview. |
| reply_markup | flags.2?ReplyMarkup | Inline keyboard |


## Type
InputBotInlineMessage

## Related pages
