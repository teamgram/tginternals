# inputInvoiceStarGift
Used to buy a Telegram Star Gift, see here » for more info.

```
inputInvoiceStarGift#e8625e92 flags:# hide_name:flags.0?true include_upgrade:flags.2?true peer:InputPeer gift_id:long message:flags.1?TextWithEntities = InputInvoice;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| hide_name | flags.0?true | If set, your name will be hidden if the destination user decides to display the gift on their profile (they will still see that you sent the gift) |
| include_upgrade | flags.2?true | Also pay for an eventual upgrade of the gift to a collectible gift ». |
| peer | InputPeer | Receiver of the gift. |
| gift_id | long | Identifier of the gift, from starGift.id |
| message | flags.1?TextWithEntities | Optional message, attached with the gift. The maximum length for this field is specified in the stargifts_message_length_max client configuration value ». |


## Type
InputInvoice

## Related pages
