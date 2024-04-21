# updateServiceNotification
A service message for the user.

```
updateServiceNotification#ebe46819 flags:# popup:flags.0?true invert_media:flags.2?true inbox_date:flags.1?int type:string message:string media:MessageMedia entities:Vector<MessageEntity> = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| popup | flags.0?true | If set, the message must be displayed in a popup. |
| invert_media | flags.2?true | If set, any eventual webpage preview will be shown on top of the message instead of at the bottom. |
| inbox_date | flags.1?int | When was the notification receivedThe message must also be stored locally as part of the message history with the user id 777000 (Telegram Notifications). |
| type | string | String, identical in format and contents to the type field in API errors. Describes type of service message. It is acceptable to ignore repeated messages of the same type within a short period of time (15 minutes). |
| message | string | Message text |
| media | MessageMedia | Media content (optional) |
| entities | Vector<MessageEntity> | Message entities for styled text |


## Type


## Related pages
