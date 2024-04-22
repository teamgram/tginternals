# Payments.GiveawayInfo
Info about a Telegram Premium Giveaway.

```
payments.giveawayInfo#4367daa0 flags:# participating:flags.0?true preparing_results:flags.3?true start_date:int joined_too_early_date:flags.1?int admin_disallowed_chat_id:flags.2?long disallowed_country:flags.4?string = payments.GiveawayInfo;
payments.giveawayInfoResults#cd5570 flags:# winner:flags.0?true refunded:flags.1?true start_date:int gift_code_slug:flags.0?string finish_date:int winners_count:int activated_count:int = payments.GiveawayInfo;

---functions---

payments.getGiveawayInfo#f4239425 peer:InputPeer msg_id:int = payments.GiveawayInfo;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| payments.giveawayInfo | Contains info about an ongoing giveaway.If neither the participating, joined_too_early_date, admin_disallowed_chat_id or disallowed_country flags are set, the user is not currently participating in the giveaway but could participate by joining all the channels specified in the messageMediaGiveaway.channels field. |
| payments.giveawayInfoResults | A giveaway has ended. |


## Methods
| Method | Description |
| ---- | ----------- |
| payments.getGiveawayInfo | Obtain information about a Telegram Premium giveaway ». |


