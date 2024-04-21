# messages.searchCustomEmoji
Look for custom emojis associated to a UTF8 emoji

```
emojiListNotModified#481eadfa = EmojiList;
emojiList#7a1e11d1 hash:long document_id:Vector<long> = EmojiList;
---functions---
messages.searchCustomEmoji#2c11c0d7 emoticon:string hash:long = EmojiList;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| emoticon | string | The emoji |
| hash | long | Hash for pagination, for more info click here |


## Result
EmojiList

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | EMOTICON_EMPTY | The emoji is empty. |

