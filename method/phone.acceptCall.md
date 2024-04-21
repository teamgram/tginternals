# phone.acceptCall
Accept incoming call

```
phone.phoneCall#ec82e140 phone_call:PhoneCall users:Vector<User> = phone.PhoneCall;
---functions---
phone.acceptCall#3bd2b4a0 peer:InputPhoneCall g_b:bytes protocol:PhoneCallProtocol = phone.PhoneCall;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPhoneCall | The call to accept |
| g_b | bytes | Parameter for E2E encryption key exchange » |
| protocol | PhoneCallProtocol | Phone call settings |


## Result
phone.PhoneCall

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CALL_ALREADY_ACCEPTED | The call was already accepted. |
| 400 | CALL_ALREADY_DECLINED | The call was already declined. |
| 500 | CALL_OCCUPY_FAILED | The call failed because the user is already making another call. |
| 400 | CALL_PEER_INVALID | The provided call peer object is invalid. |
| 406 | CALL_PROTOCOL_COMPAT_LAYER_INVALID | The other side of the call does not support any of the VoIP protocols supported by the local client, as specified by the protocol.layer and protocol.library_versions fields. |
| 400 | CALL_PROTOCOL_FLAGS_INVALID | Call protocol flags invalid. |

