# inputMediaInvoice
Generated invoice of a bot payment

```
inputMediaInvoice#8eb5a6d5 flags:# title:string description:string photo:flags.0?InputWebDocument invoice:Invoice payload:bytes provider:string provider_data:DataJSON start_param:flags.1?string extended_media:flags.2?InputMedia = InputMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| title | string | Product name, 1-32 characters |
| description | string | Product description, 1-255 characters |
| photo | flags.0?InputWebDocument | URL of the product photo for the invoice. Can be a photo of the goods or a marketing image for a service. People like it better when they see what they are paying for. |
| invoice | Invoice | The actual invoice |
| payload | bytes | Bot-defined invoice payload, 1-128 bytes. This will not be displayed to the user, use for your internal processes. |
| provider | string | Payments provider token, obtained via Botfather |
| provider_data | DataJSON | JSON-encoded data about the invoice, which will be shared with the payment provider. A detailed description of required fields should be provided by the payment provider. |
| start_param | flags.1?string | Unique bot deep links start parameter. If present, forwarded copies of the sent message will have a URL button with a deep link to the bot (instead of a Pay button), with the value used as the start parameter. If absent, forwarded copies of the sent message will have a Pay button, allowing multiple users to pay directly from the forwarded message, using the same invoice. |
| extended_media | flags.2?InputMedia | Extended media |


## Type
InputMedia

## Related pages
