# phoneConnectionWebrtc
WebRTC connection parameters

```
phoneConnectionWebrtc#635fe375 flags:# turn:flags.0?true stun:flags.1?true id:long ip:string ipv6:string port:int username:string password:string = PhoneConnection;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| turn | flags.0?true | Whether this is a TURN endpoint |
| stun | flags.1?true | Whether this is a STUN endpoint |
| id | long | Endpoint ID |
| ip | string | IP address |
| ipv6 | string | IPv6 address |
| port | int | Port |
| username | string | Username |
| password | string | Password |


## Type
PhoneConnection

## Related pages
