# auth.sentCodeTypeSetUpEmailRequired
The user should add and verify an email address in order to login as described here ».

```
auth.sentCodeTypeSetUpEmailRequired#a5491dea flags:# apple_signin_allowed:flags.0?true google_signin_allowed:flags.1?true = auth.SentCodeType;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| apple_signin_allowed | flags.0?true | Whether authorization through Apple ID is allowed |
| google_signin_allowed | flags.1?true | Whether authorization through Google ID is allowed |


## Type
auth.SentCodeType

## Related pages
