# inputInvoicePremiumGiftCode
Used if the user wishes to start a channel giveaway or send some giftcodes to members of a channel, in exchange for boosts.

```
inputInvoicePremiumGiftCode#98986c0d purpose:InputStorePaymentPurpose option:PremiumGiftCodeOption = InputInvoice;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| purpose | InputStorePaymentPurpose | Should be populated with inputStorePaymentPremiumGiveaway for giveaways and inputStorePaymentPremiumGiftCode for gifts. |
| option | PremiumGiftCodeOption | Should be populated with one of the giveaway options returned by payments.getPremiumGiftCodeOptions, see the giveaways » documentation for more info. |


## Type
InputInvoice

## Related pages
