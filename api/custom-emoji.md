# Custom emojis

Telegram allows including animated and static custom emojis inside of messages.

### Custom emoji entities

```
messageEntityCustomEmoji#c8cf05f8 offset:int length:int document_id:long = MessageEntity;

document#8fd4c4d8 flags:# id:long access_hash:long file_reference:bytes date:int mime_type:string size:long thumbs:flags.0?Vector<PhotoSize> video_thumbs:flags.1?Vector<VideoSize> dc_id:int attributes:Vector<DocumentAttribute> = Document;

documentAttributeCustomEmoji#fd149899 flags:# free:flags.0?true text_color:flags.1?true alt:string stickerset:InputStickerSet = DocumentAttribute;

---functions---

messages.getCustomEmojiDocuments#d9ab0f54 document_id:Vector<long> = Vector<Document>;
```

Custom emojis are a special kind of entity », containing just a document_id, which can be passed to messages.getCustomEmojiDocuments to fetch the static, animated or video sticker emoji that should be displayed to the user as described in the stickers documentation.

Custom emoji documents will contain documentAttributeCustomEmoji attribute instead of a documentAttributeSticker, containing information on the associated emoji (alt), whether the emoji can be used by non-premium users (free) and the associated stickerset.
If the documentAttributeCustomEmoji.text_color flag is set, the color of this TGS custom emoji should be changed to the text color when used in messages, the accent color if used as emoji status, white on chat photos, or another appropriate color based on context.

Note that when sending messages with attached custom emojis, the messageEntityCustomEmoji entity » must wrap exactly one regular emoji (the one contained in documentAttributeCustomEmoji.alt) in the related text, otherwise the server will ignore it.

Like stickers, custom emojis are organized in stickersets: see the stickers documentation » for more info on how to work with them.

To send a message with one or more custom emojis, create and attach messageEntityCustomEmoji entities » to a message.
Note that you can attach a maximum of message_animated_emoji_max custom emojis, as specified by the appConfig field ».

### Emoji categories

The custom emoji selection UI should offer a list of categories to quickly filter results by a (list of) emojis, or by some other criteria, see here » for more info.

### Emoji keywords

```
emojiKeyword#d5b3b9f9 keyword:string emoticons:Vector<string> = EmojiKeyword;
emojiKeywordDeleted#236df622 keyword:string emoticons:Vector<string> = EmojiKeyword;

emojiKeywordsDifference#5cc761bd lang_code:string from_version:int version:int keywords:Vector<EmojiKeyword> = EmojiKeywordsDifference;

emojiLanguage#b3fb5361 lang_code:string = EmojiLanguage;
emojiURL#a575739d url:string = EmojiURL;

---functions---

messages.getEmojiKeywords#35a0e062 lang_code:string = EmojiKeywordsDifference;
messages.getEmojiKeywordsDifference#1508b6af lang_code:string from_version:int = EmojiKeywordsDifference;
messages.getEmojiKeywordsLanguages#4e9963b2 lang_codes:Vector<string> = Vector<EmojiLanguage>;

messages.getEmojiURL#d5b10c26 lang_code:string = EmojiURL;
```

First of all, invoke messages.getEmojiKeywordsLanguages to obtain a list of languages that must be used when fetching emoji keyword lists: usually the method will return the passed language codes (if localized) + en + some language codes for similar languages (if applicable).
Then, invoke messages.getEmojiKeywords for all the returned language codes to fetch localized lists of keywords, associated to UTF-8 emojis.

Use the returned keywords to allow users to search both emojis and custom emojis by keyword, by displaying both the UTF-8 emojis associated to the keyword and the custom emojis associated to those UTF-8 emojis.

Invoke messages.getEmojiKeywordsDifference regularly to fetch updates to locally stored keyword lists for all languages.

messages.getEmojiURL may be used to fetch an HTTP URL which can be used to automatically log in into translation platform and suggest new emoji keywords: the URL will be valid for 30 seconds after generation.

Additionally, custom emojis and non-mask stickers may also have a set of custom keywords, returned in the custom emoji stickerset information:

```
stickerKeyword#fcfeb29c document_id:long keyword:Vector<string> = StickerKeyword;

messages.stickerSet#6e153f16 set:StickerSet packs:Vector<StickerPack> keywords:Vector<StickerKeyword> documents:Vector<Document> = messages.StickerSet;

stickerSetFullCovered#40d13c0e set:StickerSet packs:Vector<StickerPack> keywords:Vector<StickerKeyword> documents:Vector<Document> = StickerSetCovered;
```

