# messageMediaInvoice
Invoice

```
messageMediaInvoice#f6a548d3 flags:# shipping_address_requested:flags.1?true test:flags.3?true title:string description:string photo:flags.0?WebDocument receipt_msg_id:flags.2?int currency:string total_amount:long start_param:string extended_media:flags.4?MessageExtendedMedia = MessageMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| shipping_address_requested | flags.1?true | Whether the shipping address was requested |
| test | flags.3?true | Whether this is an example invoice |
| title | string | Product name, 1-32 characters |
| description | string | Product description, 1-255 characters |
| photo | flags.0?WebDocument | URL of the product photo for the invoice. Can be a photo of the goods or a marketing image for a service. People like it better when they see what they are paying for. |
| receipt_msg_id | flags.2?int | Message ID of receipt: if set, clients should change the text of the first keyboardButtonBuy button always attached to the message to a localized version of the word Receipt |
| currency | string | Three-letter ISO 4217 currency code |
| total_amount | long | Total price in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |
| start_param | string | Unique bot deep-linking parameter that can be used to generate this invoice |
| extended_media | flags.4?MessageExtendedMedia | Extended media |


## Type
MessageMedia

## Related pages
