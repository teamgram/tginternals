# inputBusinessGreetingMessage
Describes a Telegram Business greeting, automatically sent to new users writing to us in private for the first time, or after a certain inactivity period.

```
inputBusinessGreetingMessage#194cb3b shortcut_id:int recipients:InputBusinessRecipients no_activity_days:int = InputBusinessGreetingMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| shortcut_id | int | ID of a quick reply shorcut, containing the greeting messages to send, see here » for more info. |
| recipients | InputBusinessRecipients | Allowed recipients for the greeting messages. |
| no_activity_days | int | The number of days after which a private chat will be considered as inactive; currently, must be one of 7, 14, 21, or 28. |


## Type
InputBusinessGreetingMessage

## Related pages
