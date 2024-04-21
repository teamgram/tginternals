# botInlineMessageText
Send a simple text message

```
botInlineMessageText#8c7f65e2 flags:# no_webpage:flags.0?true invert_media:flags.3?true message:string entities:flags.1?Vector<MessageEntity> reply_markup:flags.2?ReplyMarkup = BotInlineMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| no_webpage | flags.0?true | Disable webpage preview |
| invert_media | flags.3?true | If set, any eventual webpage preview will be shown on top of the message instead of at the bottom. |
| message | string | The message |
| entities | flags.1?Vector<MessageEntity> | Message entities for styled text |
| reply_markup | flags.2?ReplyMarkup | Inline keyboard |


## Type
BotInlineMessage

## Related pages
