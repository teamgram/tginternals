# updateStickerSets
Installed stickersets have changed, the client should refetch them as described in the docs.

```
updateStickerSets#31c24808 flags:# masks:flags.0?true emojis:flags.1?true = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| masks | flags.0?true | Whether mask stickersets have changed |
| emojis | flags.1?true | Whether the list of installed custom emoji stickersets has changed |


## Type
Update

## Related pages
