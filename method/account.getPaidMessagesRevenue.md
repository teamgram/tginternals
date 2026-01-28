# account.getPaidMessagesRevenue
Get the number of stars we have received from the specified user thanks to paid messages »; the received amount will be equal to the sent amount multiplied by stars_paid_message_commission_permille divided by 1000.

```
account.paidMessagesRevenue#1e109708 stars_amount:long = account.PaidMessagesRevenue;
---functions---
account.getPaidMessagesRevenue#19ba4a67 flags:# parent_peer:flags.0?InputPeer user_id:InputUser = account.PaidMessagesRevenue;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| parent_peer | flags.0?InputPeer | If set, can contain the ID of a monoforum (channel direct messages) to obtain the number of stars the user has spent to send us direct messages via the channel. |
| user_id | InputUser | The user that paid to send us messages. |


## Result
account.PaidMessagesRevenue

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PARENT_PEER_INVALID | The specified parent_peer is invalid. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

