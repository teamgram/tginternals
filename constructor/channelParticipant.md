# channelParticipant
Channel/supergroup participant

```
channelParticipant#cb397619 flags:# user_id:long date:int subscription_until_date:flags.0?int = ChannelParticipant;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| user_id | long | Participant user ID |
| date | int | Date joined |
| subscription_until_date | flags.0?int | If set, contains the expiration date of the current Telegram Star subscription period » for the specified participant. |


## Type
ChannelParticipant

## Related pages
