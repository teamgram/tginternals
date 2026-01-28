# starGiftAttributeOriginalDetails
Info about the sender, receiver and message attached to the original gift », before it was upgraded to a collectible gift ».

```
starGiftAttributeOriginalDetails#e0bff26c flags:# sender_id:flags.0?Peer recipient_id:Peer date:int message:flags.1?TextWithEntities = StarGiftAttribute;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| sender_id | flags.0?Peer | Original sender of the gift, absent if the gift was private. |
| recipient_id | Peer | Original receiver of the gift. |
| date | int | When was the gift sent. |
| message | flags.1?TextWithEntities | Original message attached to the gift, if present. |


## Type
StarGiftAttribute

## Related pages
