# updateNewAuthorization
A new session logged into the current user's account through an unknown device.

```
updateNewAuthorization#8951abef flags:# unconfirmed:flags.0?true hash:long date:flags.0?int device:flags.0?string location:flags.0?string = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| unconfirmed | flags.0?true | Whether the session is unconfirmed, see here » for more info. |
| hash | long | Hash for pagination, for more info click here |
| date | flags.0?int | Authorization date |
| device | flags.0?string | Name of device, for example Android |
| location | flags.0?string | Location, for example USA, NY (IP=1.2.3.4) |


## Type
Update

## Related pages
