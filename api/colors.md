# Accent colors

Telegram users and channels can change the accent color and background pattern of their profile page and their messages!

Schema:

```
peerColor#b54b5acf flags:# color:flags.0?int background_emoji_id:flags.1?long = PeerColor;

help.peerColorSet#26219a58 colors:Vector<int> = help.PeerColorSet;
help.peerColorProfileSet#767d61eb palette_colors:Vector<int> bg_colors:Vector<int> story_colors:Vector<int> = help.PeerColorSet;

help.peerColorOption#adec6ebe flags:# hidden:flags.0?true color_id:int colors:flags.1?help.PeerColorSet dark_colors:flags.2?help.PeerColorSet channel_min_level:flags.3?int group_min_level:flags.4?int = help.PeerColorOption;

help.peerColorsNotModified#2ba1f5ce = help.PeerColors;
help.peerColors#00f8ed08 hash:int colors:Vector<help.PeerColorOption> = help.PeerColors;

stickerSet#2dd14edc flags:# archived:flags.1?true official:flags.2?true masks:flags.3?true emojis:flags.7?true text_color:flags.9?true channel_emoji_status:flags.10?true creator:flags.11?true installed_date:flags.0?int id:long access_hash:long title:string short_name:string thumbs:flags.4?Vector<PhotoSize> thumb_dc_id:flags.4?int thumb_version:flags.4?int thumb_document_id:flags.8?long count:int hash:int = StickerSet;

user#20b1422 flags:# self:flags.10?true contact:flags.11?true mutual_contact:flags.12?true deleted:flags.13?true bot:flags.14?true bot_chat_history:flags.15?true bot_nochats:flags.16?true verified:flags.17?true restricted:flags.18?true min:flags.20?true bot_inline_geo:flags.21?true support:flags.23?true scam:flags.24?true apply_min_photo:flags.25?true fake:flags.26?true bot_attach_menu:flags.27?true premium:flags.28?true attach_menu_enabled:flags.29?true flags2:# bot_can_edit:flags2.1?true close_friend:flags2.2?true stories_hidden:flags2.3?true stories_unavailable:flags2.4?true contact_require_premium:flags2.10?true bot_business:flags2.11?true bot_has_main_app:flags2.13?true id:long access_hash:flags.0?long first_name:flags.1?string last_name:flags.2?string username:flags.3?string phone:flags.4?string photo:flags.5?UserProfilePhoto status:flags.6?UserStatus bot_info_version:flags.14?int restriction_reason:flags.18?Vector<RestrictionReason> bot_inline_placeholder:flags.19?string lang_code:flags.22?string emoji_status:flags.30?EmojiStatus usernames:flags2.0?Vector<Username> stories_max_id:flags2.5?int color:flags2.8?PeerColor profile_color:flags2.9?PeerColor bot_active_users:flags2.12?int bot_verification_icon:flags2.14?long send_paid_messages_stars:flags2.15?long = User;

channel#fe685355 flags:# creator:flags.0?true left:flags.2?true broadcast:flags.5?true verified:flags.7?true megagroup:flags.8?true restricted:flags.9?true signatures:flags.11?true min:flags.12?true scam:flags.19?true has_link:flags.20?true has_geo:flags.21?true slowmode_enabled:flags.22?true call_active:flags.23?true call_not_empty:flags.24?true fake:flags.25?true gigagroup:flags.26?true noforwards:flags.27?true join_to_send:flags.28?true join_request:flags.29?true forum:flags.30?true flags2:# stories_hidden:flags2.1?true stories_hidden_min:flags2.2?true stories_unavailable:flags2.3?true signature_profiles:flags2.12?true autotranslation:flags2.15?true broadcast_messages_allowed:flags2.16?true monoforum:flags2.17?true forum_tabs:flags2.19?true id:long access_hash:flags.13?long title:string username:flags.6?string photo:ChatPhoto date:int restriction_reason:flags.9?Vector<RestrictionReason> admin_rights:flags.14?ChatAdminRights banned_rights:flags.15?ChatBannedRights default_banned_rights:flags.18?ChatBannedRights participants_count:flags.17?int usernames:flags2.0?Vector<Username> stories_max_id:flags2.4?int color:flags2.7?PeerColor profile_color:flags2.8?PeerColor emoji_status:flags2.9?EmojiStatus level:flags2.10?int subscription_until_date:flags2.11?int bot_verification_icon:flags2.13?long send_paid_messages_stars:flags2.14?long linked_monoforum_id:flags2.18?long = Chat;

---functions---

help.getPeerColors#da80f42f hash:int = help.PeerColors;
help.getPeerProfileColors#abcfa9fd hash:int = help.PeerColors;

account.getDefaultBackgroundEmojis#a60ab9ce hash:long = EmojiList;

account.updateColor#7cefa15d flags:# for_profile:flags.1?true color:flags.2?int background_emoji_id:flags.0?long = Bool;

channels.updateColor#d8aa3671 flags:# for_profile:flags.1?true channel:InputChannel color:flags.2?int background_emoji_id:flags.0?long = Updates;
```

A peerColor constructor contains a color palette ID (id) and a custom emoji sticker » (background_emoji) to be re-colored using the colors in the palette and spread out throughout the palette, generating a background that can be used in the profile page of a user, and in other places throughout the UI, namely in in webpage preview message frames and message accent colors when quoting or replying to messages sent by a channel or user that enabled a custom message accents.

The color palettes is identified by an id (not by an RGB24 color); use help.getPeerProfileColors to obtain all color palettes (represented by help.peerColorOption constructors) that can be used in the background of a profile page, and use help.getPeerColors to obtain all color palettes that can be used in message accents.

A color palette is represented by a help.peerColorOption constructor: the palette ID is contained in color_id; the palette for light mode is contained in the colors field, the palette for dark mode is contained in the dark_colors field.
If the hidden flag is set it should not be displayed as an option to the user when choosing a palette to use in the profile page or in message accents.

The actual colors that should be used are contained either in a help.peerColorSet (returned by help.getPeerColors, containing a palette for message accents) or in a help.peerColorProfileSet (returned by help.getPeerColors containing a palette for profile pages), see the relative constructor pages for more info.

Use account.getDefaultBackgroundEmojis to obtain a list of IDs of custom emojis that can be used in a palette background.

All custom emojis in custom emoji stickersets » with text_color flag set can also be used for the same purpose.

Use account.updateColor to update the color palette of the current account's message accents and/or profile page; note that the current account must be subscribed to Telegram Premium in order to call the method.
Use channels.updateColor to update the color palette of a channel/supergroup's profile page accents, or a channel's message accent.

Note that channels/supergroups can use a message accent palette or profile palette only after reaching at least the boost level specified in the channel_min_level/group_min_level field of the help.peerColorOption constructor for the chosen palette.

Additionally, to change profile palettes, channels/supergroups must also reach at least the boost level specified in the channel_profile_bg_icon_level_min »/group_profile_bg_icon_level_min » config parameters.

The chosen message accent palette will be visible to other users in the channel.color and user.color fields; changing it will emit an updateChannel/updateUser update.

The chosen profile palettes will be visible in the user.profile_color and channel.profile_color fields; changing it will emit an updateUser update/updateChannel update.

If no palette is specified for a peer, a random color from red, orange, violet, green, cyan, blue, pink (eventually tweaked according to the client's theme) must be chosen locally as message accent palette once for every met peer.

