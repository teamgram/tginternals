# Emoji status

Telegram allows users, channels and supergroups to set an emoticon or a custom emoji as status, to show next to their name in chats and profiles.

### Setting an emoji status

```
emojiStatusEmpty#2de11aae = EmojiStatus;
emojiStatus#e7ff068a flags:# document_id:long until:flags.0?int = EmojiStatus;
inputEmojiStatusCollectible#7141dbf flags:# collectible_id:long until:flags.0?int = EmojiStatus;

emojiStatusCollectible#7184603b flags:# collectible_id:long document_id:long title:string slug:string pattern_document_id:long center_color:int edge_color:int pattern_color:int text_color:int until:flags.0?int = EmojiStatus;

user#20b1422 flags:# self:flags.10?true contact:flags.11?true mutual_contact:flags.12?true deleted:flags.13?true bot:flags.14?true bot_chat_history:flags.15?true bot_nochats:flags.16?true verified:flags.17?true restricted:flags.18?true min:flags.20?true bot_inline_geo:flags.21?true support:flags.23?true scam:flags.24?true apply_min_photo:flags.25?true fake:flags.26?true bot_attach_menu:flags.27?true premium:flags.28?true attach_menu_enabled:flags.29?true flags2:# bot_can_edit:flags2.1?true close_friend:flags2.2?true stories_hidden:flags2.3?true stories_unavailable:flags2.4?true contact_require_premium:flags2.10?true bot_business:flags2.11?true bot_has_main_app:flags2.13?true id:long access_hash:flags.0?long first_name:flags.1?string last_name:flags.2?string username:flags.3?string phone:flags.4?string photo:flags.5?UserProfilePhoto status:flags.6?UserStatus bot_info_version:flags.14?int restriction_reason:flags.18?Vector<RestrictionReason> bot_inline_placeholder:flags.19?string lang_code:flags.22?string emoji_status:flags.30?EmojiStatus usernames:flags2.0?Vector<Username> stories_max_id:flags2.5?int color:flags2.8?PeerColor profile_color:flags2.9?PeerColor bot_active_users:flags2.12?int bot_verification_icon:flags2.14?long send_paid_messages_stars:flags2.15?long = User;

updateUserEmojiStatus#28373599 user_id:long emoji_status:EmojiStatus = Update;

updateRecentEmojiStatuses#30f443db = Update;

account.emojiStatusesNotModified#d08ce645 = account.EmojiStatuses;
account.emojiStatuses#90c467d1 hash:long statuses:Vector<EmojiStatus> = account.EmojiStatuses;

---functions---

account.updateEmojiStatus#fbd3de6b emoji_status:EmojiStatus = Bool;
account.getRecentEmojiStatuses#0f578105 hash:long = account.EmojiStatuses;
account.clearRecentEmojiStatuses#18201aae = Bool;
```

Use account.updateEmojiStatus to change the status emoji of your profile.

- Pass emojiStatus to set a custom emoji.

- Pass inputEmojiStatusCollectible to set an owned collectible gift » as emoji status.

- Note that once set, the status will be returned to users as a emojiStatusCollectible constructor, instead (which cannot be passed to account.updateEmojiStatus, and must be converted to an inputEmojiStatusCollectible first).

- The emoji status will also alter some properties of the profile page itself through pattern_document_id, and the other fields.

- Pass emojiStatusEmpty to remove the currently set custom emoji.

The newly set EmojiStatus constructor will be contained in the emoji_status field of the user constructor, and other users will receive an updateUserEmojiStatus.

Other logged-in clients will also receive an updateRecentEmojiStatuses update, indicating that the recent status emoji list has changed.

Recently used emoji statuses can be fetched using account.getRecentEmojiStatuses, and the list can be cleared using account.clearRecentEmojiStatuses.

Note that the custom emoji selection UI should offer a list of categories to quickly filter results by a (list of) emojis, or by some other criteria, see here » for more info.

#### Setting an emoji status in channels and supergroups

```
emojiList#7a1e11d1 hash:long document_id:Vector<long> = EmojiList;

---functions---

account.getChannelRestrictedStatusEmojis#35a9e0d5 hash:long = EmojiList;
```

Only channel/supergroup custom emoji stickersets, i.e. stickersets with the channel_emoji_status flag set, can be used in channel/supergroup custom emoji statuses.

Note, however, that some specific custom emojis from channel/supergroup custom emoji stickersets cannot be used as channel/supergroup statuses: use account.getChannelRestrictedStatusEmojis to fetch the full list of IDs of custom emojis that cannot be used in channel/supergroup statuses.

Channels/supergroups gain the ability to change their status emoji only after reaching at least the boost level specified in the channel_emoji_status_level_min »/group_emoji_status_level_min » config parameters.

#### Setting an emoji status from a bot

```
userFull#c577b5ad flags:# blocked:flags.0?true phone_calls_available:flags.4?true phone_calls_private:flags.5?true can_pin_message:flags.7?true has_scheduled:flags.12?true video_calls_available:flags.13?true voice_messages_forbidden:flags.20?true translations_disabled:flags.23?true stories_pinned_available:flags.26?true blocked_my_stories_from:flags.27?true wallpaper_overridden:flags.28?true contact_require_premium:flags.29?true read_dates_private:flags.30?true flags2:# sponsored_enabled:flags2.7?true can_view_revenue:flags2.9?true bot_can_manage_emoji_status:flags2.10?true display_gifts_button:flags2.16?true id:long about:flags.1?string settings:PeerSettings personal_photo:flags.21?Photo profile_photo:flags.2?Photo fallback_photo:flags.22?Photo notify_settings:PeerNotifySettings bot_info:flags.3?BotInfo pinned_msg_id:flags.6?int common_chats_count:int folder_id:flags.11?int ttl_period:flags.14?int theme:flags.15?ChatTheme private_forward_name:flags.16?string bot_group_admin_rights:flags.17?ChatAdminRights bot_broadcast_admin_rights:flags.18?ChatAdminRights wallpaper:flags.24?WallPaper stories:flags.25?PeerStories business_work_hours:flags2.0?BusinessWorkHours business_location:flags2.1?BusinessLocation business_greeting_message:flags2.2?BusinessGreetingMessage business_away_message:flags2.3?BusinessAwayMessage business_intro:flags2.4?BusinessIntro birthday:flags2.5?Birthday personal_channel_id:flags2.6?long personal_channel_message:flags2.6?int stargifts_count:flags2.8?int starref_program:flags2.11?StarRefProgram bot_verification:flags2.12?BotVerification send_paid_messages_stars:flags2.14?long disallowed_gifts:flags2.15?DisallowedGiftsSettings stars_rating:flags2.17?StarsRating stars_my_pending_rating:flags2.18?StarsRating stars_my_pending_rating_date:flags2.18?int main_tab:flags2.20?ProfileTab saved_music:flags2.21?Document = UserFull;

---functions---

bots.updateUserEmojiStatus#ed9f30c5 user_id:InputUser emoji_status:EmojiStatus = Bool;
bots.toggleUserEmojiStatusPermission#06de6392 bot:InputUser enabled:Bool = Bool;
```

Bots can set the emoji status of a user in two ways.

- By emitting a web_app_set_emoji_status event in a mini app, containing the ID of the custom emoji to use as status, and an optional TTL for the status, see here » for more info on the event.

- By using bots.updateUserEmojiStatus: to use this method, bots must first ask and obtain permission from the user to manage their emoji status without using explicit web_app_set_emoji_status events.

- To request permission, emit a web_app_request_emoji_status_access, and follow the full flow », which on success, leads the user to invoke the bots.toggleUserEmojiStatusPermission method, passing enabled=true and the ID of the bot.

- Once permission is obtained, the userFull.bot_can_manage_emoji_status flag of the bot will be set for the user, and the bots.updateUserEmojiStatus may be invoked by the bot to change the emoji status of the user.

### Featured emoji status stickersets

```
emojiStatus#e7ff068a flags:# document_id:long until:flags.0?int = EmojiStatus;

account.emojiStatusesNotModified#d08ce645 = account.EmojiStatuses;
account.emojiStatuses#90c467d1 hash:long statuses:Vector<EmojiStatus> = account.EmojiStatuses;

inputStickerSetEmojiDefaultStatuses#29d0f5ee = InputStickerSet;
inputStickerSetEmojiChannelDefaultStatuses#49748553 = InputStickerSet;

---functions---

account.getDefaultEmojiStatuses#d6753386 hash:long = account.EmojiStatuses;
account.getChannelDefaultEmojiStatuses#7727a7d5 hash:long = account.EmojiStatuses;
```

A set of standard statuses for users/(channels/supergroups) can be fetched by passing inputStickerSetEmojiDefaultStatuses/inputStickerSetEmojiChannelDefaultStatuses to messages.getStickerSet, as specified in the stickerset documentation ».

account.getDefaultEmojiStatuses can also be used to get a list of featured emoji statuses, from multiple featured custom emoji stickersets.
account.getChannelDefaultEmojiStatuses is the equivalent method for channel/supergroup emoji statuses.

### Collectibles as emoji statuses

```
account.emojiStatusesNotModified#d08ce645 = account.EmojiStatuses;
account.emojiStatuses#90c467d1 hash:long statuses:Vector<EmojiStatus> = account.EmojiStatuses;

emojiStatusCollectible#7184603b flags:# collectible_id:long document_id:long title:string slug:string pattern_document_id:long center_color:int edge_color:int pattern_color:int text_color:int until:flags.0?int = EmojiStatus;

---functions---

account.getCollectibleEmojiStatuses#2e7b4543 hash:long = account.EmojiStatuses;
```

Owned collectible gifts » may be set as emoji statuses: use account.getCollectibleEmojiStatuses to obtain the list of available collectible emoji statuses (as emojiStatusCollectible objects), choose one, convert it to an inputEmojiStatusCollectible and set it as described above ».

