# phoneCall
Phone call

```
phoneCall#967f7c67 flags:# p2p_allowed:flags.5?true video:flags.6?true id:long access_hash:long date:int admin_id:long participant_id:long g_a_or_b:bytes key_fingerprint:long protocol:PhoneCallProtocol connections:Vector<PhoneConnection> start_date:int = PhoneCall;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| p2p_allowed | flags.5?true | Whether P2P connection to the other peer is allowed |
| video | flags.6?true | Whether this is a video call |
| id | long | Call ID |
| access_hash | long | Access hash |
| date | int | Date of creation of the call |
| admin_id | long | User ID of the creator of the call |
| participant_id | long | User ID of the other participant in the call |
| g_a_or_b | bytes | Parameter for key exchange |
| key_fingerprint | long | Key fingerprint |
| protocol | PhoneCallProtocol | Call protocol info to be passed to libtgvoip |
| connections | Vector<PhoneConnection> | List of endpoints the user can connect to to exchange call data |
| start_date | int | When was the call actually started |


## Type
PhoneCall

## Related pages
