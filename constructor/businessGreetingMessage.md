# businessGreetingMessage
Describes a Telegram Business greeting, automatically sent to new users writing to us in private for the first time, or after a certain inactivity period.

```
businessGreetingMessage#e519abab shortcut_id:int recipients:BusinessRecipients no_activity_days:int = BusinessGreetingMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| shortcut_id | int | ID of a quick reply shorcut, containing the greeting messages to send, see here » for more info. |
| recipients | BusinessRecipients | Allowed recipients for the greeting messages. |
| no_activity_days | int | The number of days after which a private chat will be considered as inactive; currently, must be one of 7, 14, 21, or 28. |


## Type
BusinessGreetingMessage

## Related pages
