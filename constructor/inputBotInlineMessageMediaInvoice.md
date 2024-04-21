# inputBotInlineMessageMediaInvoice
An invoice

```
inputBotInlineMessageMediaInvoice#d7e78225 flags:# title:string description:string photo:flags.0?InputWebDocument invoice:Invoice payload:bytes provider:string provider_data:DataJSON reply_markup:flags.2?ReplyMarkup = InputBotInlineMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| title | string | Product name, 1-32 characters |
| description | string | Product description, 1-255 characters |
| photo | flags.0?InputWebDocument | Invoice photo |
| invoice | Invoice | The invoice |
| payload | bytes | Bot-defined invoice payload, 1-128 bytes. This will not be displayed to the user, use for your internal processes. |
| provider | string | Payments provider token, obtained via Botfather |
| provider_data | DataJSON | A JSON-serialized object for data about the invoice, which will be shared with the payment provider. A detailed description of the required fields should be provided by the payment provider. |
| reply_markup | flags.2?ReplyMarkup | Inline keyboard |


## Type
InputBotInlineMessage

## Related pages
