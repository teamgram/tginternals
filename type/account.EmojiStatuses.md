# account.EmojiStatuses
A list of emoji statuses

```
account.emojiStatusesNotModified#d08ce645 = account.EmojiStatuses;
account.emojiStatuses#90c467d1 hash:long statuses:Vector<EmojiStatus> = account.EmojiStatuses;

---functions---

account.getDefaultEmojiStatuses#d6753386 hash:long = account.EmojiStatuses;
account.getRecentEmojiStatuses#f578105 hash:long = account.EmojiStatuses;
account.getChannelDefaultEmojiStatuses#7727a7d5 hash:long = account.EmojiStatuses;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| account.emojiStatusesNotModified | The server-side list of emoji statuses hasn't changed |
| account.emojiStatuses | A list of emoji statuses |


## Methods
| Method | Description |
| ---- | ----------- |
| account.getDefaultEmojiStatuses | Get a list of default suggested emoji statuses |
| account.getRecentEmojiStatuses | Get recently used emoji statuses |
| account.getChannelDefaultEmojiStatuses | Get a list of default suggested channel emoji statuses. |


