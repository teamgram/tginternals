# bots.setCustomVerification
Verify a user or chat on behalf of an organization ».

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
bots.setCustomVerification#8b89dfbd flags:# enabled:flags.1?true bot:flags.0?InputUser peer:InputPeer custom_description:flags.2?string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| enabled | flags.1?true | If set, adds the verification; otherwise removes verification. |
| bot | flags.0?InputUser | Must not be set if invoked by a bot, must be set to the ID of an owned bot if invoked by a user. |
| peer | InputPeer | The peer to verify |
| custom_description | flags.2?string | Custom description for the verification, the UTF-8 length limit for this field is contained in bot_verification_description_length_limit ». If not set, Was verified by organization "organization_name" will be used as description. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_INVALID | This is not a valid bot. |
| 403 | BOT_VERIFIER_FORBIDDEN | This bot cannot assign verification icons. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

