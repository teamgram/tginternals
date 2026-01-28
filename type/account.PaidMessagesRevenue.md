# account.PaidMessagesRevenue
Total number of non-refunded Telegram Stars a user has spent on sending us messages either directly or through a channel, see here » for more info on paid messages.

```
account.paidMessagesRevenue#1e109708 stars_amount:long = account.PaidMessagesRevenue;

---functions---

account.getPaidMessagesRevenue#19ba4a67 flags:# parent_peer:flags.0?InputPeer user_id:InputUser = account.PaidMessagesRevenue;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| account.paidMessagesRevenue | Total number of non-refunded Telegram Stars a user has spent on sending us messages either directly or through a channel, see here » for more info on paid messages. |


## Methods
| Method | Description |
| ---- | ----------- |
| account.getPaidMessagesRevenue | Get the number of stars we have received from the specified user thanks to paid messages »; the received amount will be equal to the sent amount multiplied by stars_paid_message_commission_permille divided by 1000. |


