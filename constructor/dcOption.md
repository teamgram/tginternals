# dcOption
Data center

```
dcOption#18b7a10d flags:# ipv6:flags.0?true media_only:flags.1?true tcpo_only:flags.2?true cdn:flags.3?true static:flags.4?true this_port_only:flags.5?true id:int ip_address:string port:int secret:flags.10?bytes = DcOption;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| ipv6 | flags.0?true | Whether the specified IP is an IPv6 address |
| media_only | flags.1?true | Whether this DC should only be used to download or upload files |
| tcpo_only | flags.2?true | Whether this DC only supports connection with transport obfuscation |
| cdn | flags.3?true | Whether this is a CDN DC. |
| static | flags.4?true | If set, this IP should be used when connecting through a proxy |
| this_port_only | flags.5?true | If set, clients must connect using only the specified port, without trying any other port. |
| id | int | DC ID |
| ip_address | string | IP address of DC |
| port | int | Port |
| secret | flags.10?bytes | If the tcpo_only flag is set, specifies the secret to use when connecting using transport obfuscation |


## Type
DcOption

## Related pages
