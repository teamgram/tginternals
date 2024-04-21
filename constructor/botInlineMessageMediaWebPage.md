# botInlineMessageMediaWebPage
Specifies options that must be used to generate the link preview for the message, or even a standalone link preview without an attached message.

```
botInlineMessageMediaWebPage#809ad9a6 flags:# invert_media:flags.3?true force_large_media:flags.4?true force_small_media:flags.5?true manual:flags.7?true safe:flags.8?true message:string entities:flags.1?Vector<MessageEntity> url:string reply_markup:flags.2?ReplyMarkup = BotInlineMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| invert_media | flags.3?true | If set, any eventual webpage preview will be shown on top of the message instead of at the bottom. |
| force_large_media | flags.4?true | If set, specifies that a large media preview should be used. |
| force_small_media | flags.5?true | If set, specifies that a small media preview should be used. |
| manual | flags.7?true | If set, indicates that the URL used for the webpage preview was specified manually using inputMediaWebPage, and may not be related to any of the URLs specified in the message. |
| safe | flags.8?true | If set, the link can be opened directly without user confirmation. |
| message | string | The message, can be empty. |
| entities | flags.1?Vector<MessageEntity> | Message entities for styled text |
| url | string | The URL to use for the link preview. |
| reply_markup | flags.2?ReplyMarkup | Reply markup for sending bot buttons |


## Type
BotInlineMessage

## Related pages
