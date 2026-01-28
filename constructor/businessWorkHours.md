# businessWorkHours
Specifies a set of Telegram Business opening hours.

```
businessWorkHours#8c92b098 flags:# open_now:flags.0?true timezone_id:string weekly_open:Vector<BusinessWeeklyOpen> = BusinessWorkHours;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| open_now | flags.0?true | Ignored if set while invoking account.updateBusinessWorkHours, only returned by the server in userFull.business_work_hours, indicating whether the business is currently open according to the current time and the values in weekly_open and timezone. |
| timezone_id | string | An ID of one of the timezones returned by help.getTimezonesList.    The timezone ID is contained timezone.id, a human-readable, localized name of the timezone is available in timezone.name and the timezone.utc_offset field contains the UTC offset in seconds, which may be displayed in hh:mm format by the client together with the human-readable name (i.e. $name UTC -01:00). |
| weekly_open | Vector<BusinessWeeklyOpen> | A list of time intervals (max 28) represented by businessWeeklyOpen », indicating the opening hours of their business. |


## Type
BusinessWorkHours

## Related pages
