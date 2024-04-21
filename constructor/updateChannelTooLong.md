# updateChannelTooLong
There are new updates in the specified channel, the client must fetch them.
If the difference is too long or if the channel isn't currently in the states, start fetching from the specified pts.

```
updateChannelTooLong#108d941f flags:# channel_id:long pts:flags.0?int = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| channel_id | long | The channel |
| pts | flags.0?int | The PTS. |


## Type
Update

## Related pages
