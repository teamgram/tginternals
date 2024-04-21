# InputInvoice
An invoice

```
inputInvoiceMessage#c5b56859 peer:InputPeer msg_id:int = InputInvoice;
inputInvoiceSlug#c326caef slug:string = InputInvoice;
inputInvoicePremiumGiftCode#98986c0d purpose:InputStorePaymentPurpose option:PremiumGiftCodeOption = InputInvoice;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| inputInvoiceMessage | An invoice contained in a messageMediaInvoice message. |
| inputInvoiceSlug | An invoice slug taken from an invoice deep link or from the premium_invoice_slug app config parameter » |
| inputInvoicePremiumGiftCode | Used if the user wishes to start a channel giveaway or send some giftcodes to members of a channel, in exchange for boosts. |


## Methods
| Method | Description |
| ---- | ----------- |


