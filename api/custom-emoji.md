# Custom emojis
Telegram allows including animated and static custom emojis inside of messages.
Custom emojis are a special kind of entity », containing just a document_id, which can be passed to messages.getCustomEmojiDocuments to fetch the static, animated or video sticker emoji that should be displayed to the user as described in the stickers documentation.
Custom emoji documents will contain documentAttributeCustomEmoji attribute instead of a documentAttributeSticker, containing information on the associated emoji (alt), whether the emoji can be used by non-premium users (free) and the associated stickerset.
If the documentAttributeCustomEmoji.text_color flag is set, the color of this TGS custom emoji should be changed to the text color when used in messages, the accent color if used as emoji status, white on chat photos, or another appropriate color based on context.
Note that when sending messages with attached custom emojis, the messageEntityCustomEmoji entity » must wrap exactly one regular emoji (the one contained in documentAttributeCustomEmoji.alt) in the related text, otherwise the server will ignore it.
Like stickers, custom emojis are organized in stickersets: see the stickers documentation » for more info on how to work with them.
To send a message with one or more custom emojis, create and attach messageEntityCustomEmoji entities » to a message.
Note that you can attach a maximum of message_animated_emoji_max custom emojis, as specified by the appConfig field ».
### Emoji categories
messages.getEmojiGroups, messages.getEmojiStatusGroups and messages.getEmojiProfilePhotoGroups may be used to fetch a categorized list of UTF-8 emojis.
Each category is described by a title (i.e. "Animals", "Faces", "Flags"), is represented by a single custom emoji (icon_emoji_id), and contains a list of UTF-8 emojis (emoticons).
These categories should be displayed in the custom emoji search bar, and when the user clicks on them, the client should display all custom emojis matching the emoticons for that category.
messages.getEmojiStatusGroups should be used when choosing a custom emoji to set as emoji status, messages.getEmojiProfilePhotoGroups when choosing a custom emoji to set as profile picture, messages.getEmojiGroups in all other cases when choosing a custom emoji.
### Emoji keywords
First of all, invoke messages.getEmojiKeywordsLanguages to obtain a list of languages that must be used when fetching emoji keyword lists: usually the method will return the passed language codes (if localized) + en + some language codes for similar languages (if applicable).
Then, invoke messages.getEmojiKeywords for all the returned language codes to fetch localized lists of keywords, associated to UTF-8 emojis.
Use the returned keywords to allow users to search both emojis and custom emojis by keyword, by displaying both the UTF-8 emojis associated to the keyword and the custom emojis associated to those UTF-8 emojis.
Invoke messages.getEmojiKeywordsDifference regularly to fetch updates to locally stored keyword lists for all languages.
messages.getEmojiURL may be used to fetch an HTTP URL which can be used to automatically log in into translation platform and suggest new emoji keywords: the URL will be valid for 30 seconds after generation.
Additionally, custom emojis and non-mask stickers may also have a set of custom keywords, returned in the custom emoji stickerset information:
