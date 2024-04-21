# auth.sentCodeTypeEmailCode
The code was sent via the previously configured login email »

```
auth.sentCodeTypeEmailCode#f450f59b flags:# apple_signin_allowed:flags.0?true google_signin_allowed:flags.1?true email_pattern:string length:int reset_available_period:flags.3?int reset_pending_date:flags.4?int = auth.SentCodeType;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| apple_signin_allowed | flags.0?true | Whether authorization through Apple ID is allowed |
| google_signin_allowed | flags.1?true | Whether authorization through Google ID is allowed |
| email_pattern | string | Pattern of the email |
| length | int | Length of the sent verification code |
| reset_available_period | flags.3?int | Clients should wait for the specified amount of seconds before allowing the user to invoke auth.resetLoginEmail (will be 0 for Premium users). |
| reset_pending_date | flags.4?int | An email reset was already requested, and will occur at the specified date. |


## Type
auth.SentCodeType

## Related pages
