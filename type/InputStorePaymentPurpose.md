# InputStorePaymentPurpose
Info about a Telegram Premium purchase

```
inputStorePaymentPremiumSubscription#a6751e66 flags:# restore:flags.0?true upgrade:flags.1?true = InputStorePaymentPurpose;
inputStorePaymentGiftPremium#616f7fe8 user_id:InputUser currency:string amount:long = InputStorePaymentPurpose;
inputStorePaymentPremiumGiftCode#a3805f3f flags:# users:Vector<InputUser> boost_peer:flags.0?InputPeer currency:string amount:long = InputStorePaymentPurpose;
inputStorePaymentPremiumGiveaway#160544ca flags:# only_new_subscribers:flags.0?true winners_are_visible:flags.3?true boost_peer:InputPeer additional_peers:flags.1?Vector<InputPeer> countries_iso2:flags.2?Vector<string> prize_description:flags.4?string random_id:long until_date:int currency:string amount:long = InputStorePaymentPurpose;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| inputStorePaymentPremiumSubscription | Info about a Telegram Premium purchase |
| inputStorePaymentGiftPremium | Info about a gifted Telegram Premium purchase |
| inputStorePaymentPremiumGiftCode | Used to gift Telegram Premium subscriptions only to some specific subscribers of a channel or to some of our contacts, see here » for more info on giveaways and gifts. |
| inputStorePaymentPremiumGiveaway | Used to pay for a giveaway, see here » for more info. |


## Methods
| Method | Description |
| ---- | ----------- |


