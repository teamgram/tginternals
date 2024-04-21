# auth.sentCodeTypeMissedCall
The code will be sent via a flash phone call, that will be closed immediately. The last digits of the phone number that calls are the code that must be entered manually by the user.

```
auth.sentCodeTypeMissedCall#82006484 prefix:string length:int = auth.SentCodeType;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| prefix | string | Prefix of the phone number from which the call will be made |
| length | int | Length of the verification code |


## Type
auth.SentCodeType

## Related pages
