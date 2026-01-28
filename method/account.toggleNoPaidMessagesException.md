# account.toggleNoPaidMessagesException
Allow a user to send us messages without paying if paid messages » are enabled.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.toggleNoPaidMessagesException#fe2eda76 flags:# refund_charged:flags.0?true require_payment:flags.2?true parent_peer:flags.1?InputPeer user_id:InputUser = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| refund_charged | flags.0?true | If set and require_payment is not set, refunds the amounts the user has already paid us to send us messages (directly or via a monoforum). |
| require_payment | flags.2?true | If set, requires the user to pay in order to send us messages. Can only be set by monoforums, not users, i.e. parent_peer must be set if this flag is set; users must instead use the inputPrivacyKeyNoPaidMessages privacy setting to remove a previously added exemption. If not set, allows the user to send us messages without paying (can be unset by both monoforums and users). |
| parent_peer | flags.1?InputPeer | If set, applies the setting within the monoforum aka direct messages » (pass the ID of the monoforum, not the ID of the associated channel). |
| user_id | InputUser | The user to exempt or unexempt. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PARENT_PEER_INVALID | The specified parent_peer is invalid. |
| 400 | UNSUPPORTED | require_payment cannot be set by users, only by monoforums: users must instead use the inputPrivacyKeyNoPaidMessages privacy setting to remove a previously added exemption. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

