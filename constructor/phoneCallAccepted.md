# phoneCallAccepted
An accepted phone call

```
phoneCallAccepted#3660c311 flags:# video:flags.6?true id:long access_hash:long date:int admin_id:long participant_id:long g_b:bytes protocol:PhoneCallProtocol = PhoneCall;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| video | flags.6?true | Whether this is a video call |
| id | long | ID of accepted phone call |
| access_hash | long | Access hash of phone call |
| date | int | When was the call accepted |
| admin_id | long | ID of the call creator |
| participant_id | long | ID of the other user in the call |
| g_b | bytes | B parameter for secure E2E phone call key exchange |
| protocol | PhoneCallProtocol | Protocol to use for phone call |


## Type
PhoneCall

## Related pages
