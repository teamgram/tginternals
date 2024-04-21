# phoneCallWaiting
Incoming phone call

```
phoneCallWaiting#c5226f17 flags:# video:flags.6?true id:long access_hash:long date:int admin_id:long participant_id:long protocol:PhoneCallProtocol receive_date:flags.0?int = PhoneCall;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| video | flags.6?true | Is this a video call |
| id | long | Call ID |
| access_hash | long | Access hash |
| date | int | Date |
| admin_id | long | Admin ID |
| participant_id | long | Participant ID |
| protocol | PhoneCallProtocol | Phone call protocol info |
| receive_date | flags.0?int | When was the phone call received |


## Type
PhoneCall

## Related pages
