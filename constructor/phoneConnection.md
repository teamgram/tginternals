# phoneConnection
Identifies an endpoint that can be used to connect to the other user in a phone call

```
phoneConnection#9cc123c7 flags:# tcp:flags.0?true id:long ip:string ipv6:string port:int peer_tag:bytes = PhoneConnection;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| tcp | flags.0?true | Whether TCP should be used |
| id | long | Endpoint ID |
| ip | string | IP address of endpoint |
| ipv6 | string | IPv6 address of endpoint |
| port | int | Port ID |
| peer_tag | bytes | Our peer tag |


## Type
PhoneConnection

## Related pages
