# auth.SentCodeType
Type of the verification code that was sent

```
auth.sentCodeTypeApp#3dbb5986 length:int = auth.SentCodeType;
auth.sentCodeTypeSms#c000bba2 length:int = auth.SentCodeType;
auth.sentCodeTypeCall#5353e5a7 length:int = auth.SentCodeType;
auth.sentCodeTypeFlashCall#ab03c6d9 pattern:string = auth.SentCodeType;
auth.sentCodeTypeMissedCall#82006484 prefix:string length:int = auth.SentCodeType;
auth.sentCodeTypeEmailCode#f450f59b flags:# apple_signin_allowed:flags.0?true google_signin_allowed:flags.1?true email_pattern:string length:int reset_available_period:flags.3?int reset_pending_date:flags.4?int = auth.SentCodeType;
auth.sentCodeTypeSetUpEmailRequired#a5491dea flags:# apple_signin_allowed:flags.0?true google_signin_allowed:flags.1?true = auth.SentCodeType;
auth.sentCodeTypeFragmentSms#d9565c39 url:string length:int = auth.SentCodeType;
auth.sentCodeTypeFirebaseSms#e57b1432 flags:# nonce:flags.0?bytes receipt:flags.1?string push_timeout:flags.1?int length:int = auth.SentCodeType;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| auth.sentCodeTypeApp | The code was sent through the telegram app |
| auth.sentCodeTypeSms | The code was sent via SMS |
| auth.sentCodeTypeCall | The code will be sent via a phone call: a synthesized voice will tell the user which verification code to input. |
| auth.sentCodeTypeFlashCall | The code will be sent via a flash phone call, that will be closed immediately. The phone code will then be the phone number itself, just make sure that the phone number matches the specified pattern. |
| auth.sentCodeTypeMissedCall | The code will be sent via a flash phone call, that will be closed immediately. The last digits of the phone number that calls are the code that must be entered manually by the user. |
| auth.sentCodeTypeEmailCode | The code was sent via the previously configured login email » |
| auth.sentCodeTypeSetUpEmailRequired | The user should add and verify an email address in order to login as described here ». |
| auth.sentCodeTypeFragmentSms | The code was delivered via fragment.com. |
| auth.sentCodeTypeFirebaseSms | An authentication code should be delivered via SMS after Firebase attestation, as described in the auth documentation ». |


## Methods
| Method | Description |
| ---- | ----------- |


