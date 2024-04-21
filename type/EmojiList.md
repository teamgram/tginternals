# EmojiList
Represents a list of custom emojis.

```
emojiListNotModified#481eadfa = EmojiList;
emojiList#7a1e11d1 hash:long document_id:Vector<long> = EmojiList;

---functions---

account.getDefaultProfilePhotoEmojis#e2750328 hash:long = EmojiList;
account.getDefaultGroupPhotoEmojis#915860ae hash:long = EmojiList;
account.getDefaultBackgroundEmojis#a60ab9ce hash:long = EmojiList;
account.getChannelRestrictedStatusEmojis#35a9e0d5 hash:long = EmojiList;

messages.searchCustomEmoji#2c11c0d7 emoticon:string hash:long = EmojiList;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| emojiListNotModified | The list of custom emojis hasn't changed. |
| emojiList | Represents a list of custom emojis. |


## Methods
| Method | Description |
| ---- | ----------- |
| account.getDefaultProfilePhotoEmojis | Get a set of suggested custom emoji stickers that can be used as profile picture |
| account.getDefaultGroupPhotoEmojis | Get a set of suggested custom emoji stickers that can be used as group picture |
| messages.searchCustomEmoji | Look for custom emojis associated to a UTF8 emoji |
| account.getDefaultBackgroundEmojis | Get a set of suggested custom emoji stickers that can be used in an accent color pattern. |
| account.getChannelRestrictedStatusEmojis | Returns fetch the full list of custom emoji IDs » that cannot be used in channel emoji statuses ». |


