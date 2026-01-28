# EmojiStatus
Emoji status

```
emojiStatusEmpty#2de11aae = EmojiStatus;
emojiStatus#e7ff068a flags:# document_id:long until:flags.0?int = EmojiStatus;
emojiStatusCollectible#7184603b flags:# collectible_id:long document_id:long title:string slug:string pattern_document_id:long center_color:int edge_color:int pattern_color:int text_color:int until:flags.0?int = EmojiStatus;
inputEmojiStatusCollectible#7141dbf flags:# collectible_id:long until:flags.0?int = EmojiStatus;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| emojiStatusEmpty | No emoji status is set |
| emojiStatus | An emoji status |
| emojiStatusCollectible | An owned collectible gift » as emoji status.Cannot be passed to account.updateEmojiStatus, must be converted to an inputEmojiStatusCollectible first before passing it to that method. |
| inputEmojiStatusCollectible | An owned collectible gift » as emoji status: can only be used in account.updateEmojiStatus, is never returned by the API.Note that once set, the status will be returned to users as a emojiStatusCollectible constructor, instead (which cannot be passed to account.updateEmojiStatus, and must be converted to an inputEmojiStatusCollectible first). |


## Methods
| Method | Description |
| ---- | ----------- |


