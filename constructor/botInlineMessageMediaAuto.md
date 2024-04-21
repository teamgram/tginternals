# botInlineMessageMediaAuto
Send whatever media is attached to the botInlineMediaResult

```
botInlineMessageMediaAuto#764cf810 flags:# invert_media:flags.3?true message:string entities:flags.1?Vector<MessageEntity> reply_markup:flags.2?ReplyMarkup = BotInlineMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| invert_media | flags.3?true | If set, any eventual webpage preview will be shown on top of the message instead of at the bottom. |
| message | string | Caption |
| entities | flags.1?Vector<MessageEntity> | Message entities for styled text |
| reply_markup | flags.2?ReplyMarkup | Inline keyboard |


## Type
BotInlineMessage

## Related pages
