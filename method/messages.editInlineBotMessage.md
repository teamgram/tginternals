# messages.editInlineBotMessage
Edit an inline bot message

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.editInlineBotMessage#83557dba flags:# no_webpage:flags.1?true invert_media:flags.16?true id:InputBotInlineMessageID message:flags.11?string media:flags.14?InputMedia reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| no_webpage | flags.1?true | Disable webpage preview |
| invert_media | flags.16?true | If set, any eventual webpage preview will be shown on top of the message instead of at the bottom. |
| id | InputBotInlineMessageID | Sent inline message ID |
| message | flags.11?string | Message |
| media | flags.14?InputMedia | Media |
| reply_markup | flags.2?ReplyMarkup | Reply markup for inline keyboards |
| entities | flags.3?Vector<MessageEntity> | Message entities for styled text |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BUTTON_DATA_INVALID | The data of one or more of the buttons you provided is invalid. |
| 400 | ENTITY_BOUNDS_INVALID | A specified entity offset or length is invalid, see here » for info on how to properly compute the entity offset/length. |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | MESSAGE_NOT_MODIFIED | The provided message data is identical to the previous message data, the message wasn't modified. |

