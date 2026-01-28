# inputEmojiStatusCollectible
An owned collectible gift » as emoji status: can only be used in account.updateEmojiStatus, is never returned by the API.

```
inputEmojiStatusCollectible#7141dbf flags:# collectible_id:long until:flags.0?int = EmojiStatus;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| collectible_id | long | ID of the collectible (from starGiftUnique.id). |
| until | flags.0?int | If set, the emoji status will be active until the specified unixtime. |


## Type


## Related pages
