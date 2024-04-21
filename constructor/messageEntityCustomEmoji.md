# messageEntityCustomEmoji
Represents a custom emoji.
Note that this entity must wrap exactly one regular emoji (the one contained in documentAttributeCustomEmoji.alt) in the related text, otherwise the server will ignore it.

```
messageEntityCustomEmoji#c8cf05f8 offset:int length:int document_id:long = MessageEntity;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| offset | int | Offset of message entity within message (in UTF-16 code units) |
| length | int | Length of message entity within message (in UTF-16 code units) |
| document_id | long | Document ID of the custom emoji, use messages.getCustomEmojiDocuments to fetch the emoji animation and the actual emoji it represents. |


## Type
MessageEntity

## Related pages
