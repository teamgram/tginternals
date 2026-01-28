# emojiStatusCollectible
An owned collectible gift » as emoji status.

```
emojiStatusCollectible#7184603b flags:# collectible_id:long document_id:long title:string slug:string pattern_document_id:long center_color:int edge_color:int pattern_color:int text_color:int until:flags.0?int = EmojiStatus;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| collectible_id | long | ID of the collectible (from starGiftUnique.id). |
| document_id | long | ID of the custom emoji representing the status. |
| title | string | Name of the collectible. |
| slug | string | Unique identifier of the collectible that may be used to create a collectible gift link » for the current collectible, or to fetch further info about the collectible using payments.getUniqueStarGift. |
| pattern_document_id | long | The ID of a pattern to apply on the profile's backdrop, correlated to the starGiftAttributePattern from the gift in slug. |
| center_color | int | Color of the center of the profile backdrop in RGB24 format, from the gift's starGiftAttributeBackdrop. |
| edge_color | int | Color of the edges of the profile backdrop in RGB24 format, from the gift's starGiftAttributeBackdrop. |
| pattern_color | int | Color of the pattern_document_id applied on the profile backdrop in RGB24 format, from the gift's starGiftAttributeBackdrop. |
| text_color | int | Color of text on the profile backdrop in RGB24 format, from the gift's starGiftAttributeBackdrop. |
| until | flags.0?int | If set, the emoji status will be active until the specified unixtime. |


## Type


## Related pages
