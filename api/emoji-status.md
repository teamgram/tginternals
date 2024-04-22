# Emoji status
Telegram allows users and channels to set an emoticon or a custom emoji as status, to show next to their name in chats and profiles.
### Setting an emoji status
Use account.updateEmojiStatus to change the status emoji of your profile.
- Pass emojiStatus to set a custom emoji.
- Pass emojiStatusUntil to set a custom emoji, for a limited period of time.
- Pass emojiStatusEmpty to set the default Premium badge.
The newly set EmojiStatus constructor will be contained in the emoji_status field of the user constructor, and other users will receive an updateUserEmojiStatus.
Other logged-in clients will also receive an updateRecentEmojiStatuses update, indicating that the recent status emoji list has changed.
Recently used emoji statuses can be fetched using account.getRecentEmojiStatuses, and the list can be cleared using account.clearRecentEmojiStatuses.
#### Setting an emoji status in channels
Only channel custom emoji stickersets, i.e. stickersets with the channel_emoji_status flag set, can be used in channel custom emoji statuses.
Note, however, that some specific custom emojis from channel custom emoji stickersets cannot be used as channel statuses: use account.getChannelRestrictedStatusEmojis to fetch the full list of IDs of custom emojis that cannot be used in channel statuses.
Channels gain the ability to change their status emoji only after reaching at least the boost level specified in the channel_emoji_status_level_min config parameter.
### Featured emoji status stickersets
A set of standard statuses for users/channels can be fetched by passing inputStickerSetEmojiDefaultStatuses/inputStickerSetEmojiChannelDefaultStatuses to messages.getStickerSet, as specified in the stickerset documentation ».
account.getDefaultEmojiStatuses can also be used to get a list of featured emoji statuses, from multiple featured custom emoji stickersets.
account.getChannelDefaultEmojiStatuses is the equivalent method for channel emoji statuses.
