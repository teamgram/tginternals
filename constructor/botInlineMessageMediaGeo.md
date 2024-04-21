# botInlineMessageMediaGeo
Send a geolocation

```
botInlineMessageMediaGeo#51846fd flags:# geo:GeoPoint heading:flags.0?int period:flags.1?int proximity_notification_radius:flags.3?int reply_markup:flags.2?ReplyMarkup = BotInlineMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| geo | GeoPoint | Geolocation |
| heading | flags.0?int | For live locations, a direction in which the location moves, in degrees; 1-360. |
| period | flags.1?int | Validity period |
| proximity_notification_radius | flags.3?int | For live locations, a maximum distance to another chat member for proximity alerts, in meters (0-100000). |
| reply_markup | flags.2?ReplyMarkup | Inline keyboard |


## Type
BotInlineMessage

## Related pages
