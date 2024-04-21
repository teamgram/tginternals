# phone.confirmCall
Complete phone call E2E encryption key exchange »

```
phone.phoneCall#ec82e140 phone_call:PhoneCall users:Vector<User> = phone.PhoneCall;
---functions---
phone.confirmCall#2efe1722 peer:InputPhoneCall g_a:bytes key_fingerprint:long protocol:PhoneCallProtocol = phone.PhoneCall;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPhoneCall | The phone call |
| g_a | bytes | Parameter for E2E encryption key exchange » |
| key_fingerprint | long | Key fingerprint |
| protocol | PhoneCallProtocol | Phone call settings |


## Result
phone.PhoneCall

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CALL_ALREADY_DECLINED | The call was already declined. |
| 400 | CALL_PEER_INVALID | The provided call peer object is invalid. |

