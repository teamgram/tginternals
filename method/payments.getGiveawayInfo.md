# payments.getGiveawayInfo
Obtain information about a Telegram Premium giveaway ».

```
payments.giveawayInfo#4367daa0 flags:# participating:flags.0?true preparing_results:flags.3?true start_date:int joined_too_early_date:flags.1?int admin_disallowed_chat_id:flags.2?long disallowed_country:flags.4?string = payments.GiveawayInfo;
payments.giveawayInfoResults#cd5570 flags:# winner:flags.0?true refunded:flags.1?true start_date:int gift_code_slug:flags.0?string finish_date:int winners_count:int activated_count:int = payments.GiveawayInfo;
---functions---
payments.getGiveawayInfo#f4239425 peer:InputPeer msg_id:int = payments.GiveawayInfo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The peer where the giveaway was posted. |
| msg_id | int | Message ID of the messageActionGiveawayLaunch service message |


## Result
payments.GiveawayInfo

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

