# messageEntityBlockquote
Message entity representing a block quote.

```
messageEntityBlockquote#f1ccaaac flags:# collapsed:flags.0?true offset:int length:int = MessageEntity;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| collapsed | flags.0?true | Whether the quote is collapsed by default. |
| offset | int | Offset of message entity within message (in UTF-16 code units) |
| length | int | Length of message entity within message (in UTF-16 code units) |


## Type
MessageEntity

## Related pages
