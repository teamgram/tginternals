# businessAwayMessage
Describes a Telegram Business away message, automatically sent to users writing to us when we're offline, during closing hours, while we're on vacation, or in some other custom time period when we cannot immediately answer to the user.

```
businessAwayMessage#ef156a5c flags:# offline_only:flags.0?true shortcut_id:int schedule:BusinessAwayMessageSchedule recipients:BusinessRecipients = BusinessAwayMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| offline_only | flags.0?true | If set, the messages will not be sent if the account was online in the last 10 minutes. |
| shortcut_id | int | ID of a quick reply shorcut, containing the away messages to send, see here » for more info. |
| schedule | BusinessAwayMessageSchedule | Specifies when should the away messages be sent. |
| recipients | BusinessRecipients | Allowed recipients for the away messages. |


## Type
BusinessAwayMessage

## Related pages
