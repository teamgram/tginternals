# channelParticipantSelf
Myself

```
channelParticipantSelf#4f607bef flags:# via_request:flags.0?true user_id:long inviter_id:long date:int subscription_until_date:flags.1?int = ChannelParticipant;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| via_request | flags.0?true | Whether I joined upon specific approval of an admin |
| user_id | long | User ID |
| inviter_id | long | User that invited me to the channel/supergroup |
| date | int | When did I join the channel/supergroup |
| subscription_until_date | flags.1?int | If set, contains the expiration date of the current Telegram Star subscription period » for the specified participant. |


## Type
ChannelParticipant

## Related pages
