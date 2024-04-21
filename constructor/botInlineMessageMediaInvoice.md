# botInlineMessageMediaInvoice
Send an invoice

```
botInlineMessageMediaInvoice#354a9b09 flags:# shipping_address_requested:flags.1?true test:flags.3?true title:string description:string photo:flags.0?WebDocument currency:string total_amount:long reply_markup:flags.2?ReplyMarkup = BotInlineMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| shipping_address_requested | flags.1?true | Set this flag if you require the user's shipping address to complete the order |
| test | flags.3?true | Test invoice |
| title | string | Product name, 1-32 characters |
| description | string | Product description, 1-255 characters |
| photo | flags.0?WebDocument | Product photo |
| currency | string | Three-letter ISO 4217 currency code |
| total_amount | long | Total price in the smallest units of the currency (integer, not float/double). For example, for a price of US$ 1.45 pass amount = 145. See the exp parameter in currencies.json, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). |
| reply_markup | flags.2?ReplyMarkup | Inline keyboard |


## Type
BotInlineMessage

## Related pages
