# phoneCallRequested
Requested phone call

```
phoneCallRequested#14b0ed0c flags:# video:flags.6?true id:long access_hash:long date:int admin_id:long participant_id:long g_a_hash:bytes protocol:PhoneCallProtocol = PhoneCall;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| video | flags.6?true | Whether this is a video call |
| id | long | Phone call ID |
| access_hash | long | Access hash |
| date | int | When was the phone call created |
| admin_id | long | ID of the creator of the phone call |
| participant_id | long | ID of the other participant of the phone call |
| g_a_hash | bytes | Parameter for key exchange |
| protocol | PhoneCallProtocol | Call protocol info to be passed to libtgvoip |


## Type
PhoneCall

## Related pages
