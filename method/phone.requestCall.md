# phone.requestCall
Start a telegram phone call

```
phone.phoneCall#ec82e140 phone_call:PhoneCall users:Vector<User> = phone.PhoneCall;
---functions---
phone.requestCall#42ff96ed flags:# video:flags.0?true user_id:InputUser random_id:int g_a_hash:bytes protocol:PhoneCallProtocol = phone.PhoneCall;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| video | flags.0?true | Whether to start a video call |
| user_id | InputUser | Destination of the phone call |
| random_id | int | Random ID to avoid resending the same object |
| g_a_hash | bytes | Parameter for E2E encryption key exchange » |
| protocol | PhoneCallProtocol | Phone call settings |


## Result
phone.PhoneCall

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CALL_PROTOCOL_FLAGS_INVALID | Call protocol flags invalid. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | PARTICIPANT_VERSION_OUTDATED | The other participant does not use an up to date telegram client with support for calls. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |
| 403 | USER_IS_BLOCKED | You were blocked by this user. |
| 403 | USER_PRIVACY_RESTRICTED | The user's privacy settings do not allow you to do this. |

