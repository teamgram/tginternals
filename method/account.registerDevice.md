# account.registerDevice
Register device to receive PUSH notifications

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.registerDevice#ec86017a flags:# no_muted:flags.0?true token_type:int token:string app_sandbox:Bool secret:bytes other_uids:Vector<long> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| no_muted | flags.0?true | Avoid receiving (silent and invisible background) notifications. Useful to save battery. |
| token_type | int | Device token type, see PUSH updates for the possible values. |
| token | string | Device token, see PUSH updates for the possible values. |
| app_sandbox | Bool | If (boolTrue) is transmitted, a sandbox-certificate will be used during transmission. |
| secret | bytes | For FCM and APNS VoIP, optional encryption key used to encrypt push notifications |
| other_uids | Vector<long> | List of user identifiers of other users currently using the client |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | TOKEN_EMPTY | The specified token is empty. |
| 400 | TOKEN_INVALID | The provided token is invalid. |
| 400 | TOKEN_TYPE_INVALID | The specified token type is invalid. |
| 400 | WEBPUSH_AUTH_INVALID | The specified web push authentication secret is invalid. |
| 400 | WEBPUSH_KEY_INVALID | The specified web push elliptic curve Diffie-Hellman public key is invalid. |
| 400 | WEBPUSH_TOKEN_INVALID | The specified web push token is invalid. |

