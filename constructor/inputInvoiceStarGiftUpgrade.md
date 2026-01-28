# inputInvoiceStarGiftUpgrade
Used to pay to upgrade a Gift to a collectible gift, see the collectible gifts » documentation for more info on the full flow.

```
inputInvoiceStarGiftUpgrade#4d818d5d flags:# keep_original_details:flags.0?true stargift:InputSavedStarGift = InputInvoice;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| keep_original_details | flags.0?true | Set this flag to keep the original gift text, sender and receiver in the upgraded gift as a starGiftAttributeOriginalDetails attribute. |
| stargift | InputSavedStarGift | The identifier of the received gift to upgrade. |


## Type
InputInvoice

## Related pages
