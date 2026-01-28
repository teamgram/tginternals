# Telegram Premium

Telegram Premium is an optional subscription service that unlocks additional exclusive client-side and API-side features, while helping support the development of the app. It is a part of Telegram’s sustainable monetization – driven by our users, rather than advertisers or shareholders. This way, Telegram can remain independent and prioritize its users first.

> This page describes how should client apps handle Premium features: for a user-friendly overview of Telegram Premium features, see the Telegram Premium FAQ.

### Telegram Premium users

```
inputUserSelf#f7c1b13f = InputUser;

user#20b1422 flags:# self:flags.10?true contact:flags.11?true mutual_contact:flags.12?true deleted:flags.13?true bot:flags.14?true bot_chat_history:flags.15?true bot_nochats:flags.16?true verified:flags.17?true restricted:flags.18?true min:flags.20?true bot_inline_geo:flags.21?true support:flags.23?true scam:flags.24?true apply_min_photo:flags.25?true fake:flags.26?true bot_attach_menu:flags.27?true premium:flags.28?true attach_menu_enabled:flags.29?true flags2:# bot_can_edit:flags2.1?true close_friend:flags2.2?true stories_hidden:flags2.3?true stories_unavailable:flags2.4?true contact_require_premium:flags2.10?true bot_business:flags2.11?true bot_has_main_app:flags2.13?true id:long access_hash:flags.0?long first_name:flags.1?string last_name:flags.2?string username:flags.3?string phone:flags.4?string photo:flags.5?UserProfilePhoto status:flags.6?UserStatus bot_info_version:flags.14?int restriction_reason:flags.18?Vector<RestrictionReason> bot_inline_placeholder:flags.19?string lang_code:flags.22?string emoji_status:flags.30?EmojiStatus usernames:flags2.0?Vector<Username> stories_max_id:flags2.5?int color:flags2.8?PeerColor profile_color:flags2.9?PeerColor bot_active_users:flags2.12?int bot_verification_icon:flags2.14?long send_paid_messages_stars:flags2.15?long = User;

help.premiumPromo#5334759c status_text:string status_entities:Vector<MessageEntity> video_sections:Vector<string> videos:Vector<Document> period_options:Vector<PremiumSubscriptionOption> users:Vector<User> = help.PremiumPromo;

---functions---

users.getUsers#d91a548 id:Vector<InputUser> = Vector<User>;
help.getPremiumPromo#b81b93d4 = help.PremiumPromo;
```

Premium users will have the premium flag of the user set.

Use users.getUsers with inputUserSelf to fetch info about the current subscription status of the current user.
You can also directly use help.getPremiumPromo, as it will return info about the current user in the users field.

### Telegram Premium features

Telegram Premium offers a set of additional features and raised limits: clients should be aware of the current subscription status to accordingly modify client behavior.

#### Promo page

```
help.premiumPromo#5334759c status_text:string status_entities:Vector<MessageEntity> video_sections:Vector<string> videos:Vector<Document> period_options:Vector<PremiumSubscriptionOption> users:Vector<User> = help.PremiumPromo;

---functions---

help.getPremiumPromo#b81b93d4 = help.PremiumPromo;
help.getAppConfig#61e3f854 hash:int = help.AppConfig;
```

The help.premiumPromo constructor returned by help.getPremiumPromo contains various info about the subscription, as described in the constructor page.

Clients should show a Telegram Premium button in the settings.
Clicking on this button in the settings, clicking on the badge of a Premium user or hitting one of the Premium limits listed below should open a Telegram Premium modal.

Call help.getPremiumPromo and help.getAppConfig to fetch info on how to build the premium modal.

help.getAppConfig will return a list of Premium feature identifiers in the premium_promo_order appConfig field: the modal should contain a row for each returned feature, ordered as specified in the returned array.

These feature identifiers must be used when subscribing to Telegram Premium if the related limit was hit.

Possible feature identifiers:

##### stories

Telegram Premium adds some story-related features.

Story-related Premium features also have certain subidentifiers, which are used if the user chooses to subscribe to Telegram Premium after hitting one of the following story-related limitations.

If the user instead signs up simply after reading the promo page for story-related features, pass just stories as feature identifier.

Here's the full list of story-related features and their sub-identifiers (contained in the title header):

###### stories__priority_order

Stories posted by Premium users are shown first to users when fetching the list of active stories with stories.getAllStories ».

###### stories__stealth_mode

Premium users can activate stealth mode ».

###### stories__permanent_views_history

Premium users can fetch the full viewer list of stories, even after they expire »

###### stories__expiration_durations

Premium users can set custom expiration options when posting stories »

###### stories__save_stories_to_gallery

Premium users can save other users' unprotected stories.

###### stories__links_and_formatting

Premium users can styled text entities and links in story captions and use URL media areas, as specified by the stories_entities » config key.

###### stories__quality

Premium users can view stories in a higher quality.

There are a few more Premium story features that are listed in the limits » section.

See the stories documentation » for more information on stories.

##### double_limits

Clicking on this entry should open a secondary popup with a list of the improved Premium limits, as follows.

Limit-related Premium features also have certain subidentifiers, which are used if the user chooses to subscribe to Telegram Premium after hitting one of the following limitations.

If the user instead signs up simply after reading the promo page for limits, pass just double_limits as feature identifier.

Here's the full list of improved limits and their sub-identifiers (contained in the title header):

###### double_limits__channels

Config keys: channels_limit_premium »/channels_limit_default »

The maximum number of channels and supergroups a Premium/non-Premium user may join (integer)

###### double_limits__saved_gifs

Config keys: saved_gifs_limit_premium »/saved_gifs_limit_default »

The maximum number of GIFs a Premium/non-Premium user may save (integer)

###### double_limits__stickers_faved

Config keys: stickers_faved_limit_premium »/stickers_faved_limit_default »

The maximum number of stickers a Premium/non-Premium user may add to Favorites » (integer)

###### double_limits__dialog_filters

Config keys: dialog_filters_limit_premium »/dialog_filters_limit_default »

The maximum number of folders a Premium/non-Premium user may create (integer)

###### double_limits__dialog_filters_chats

Config keys: dialog_filters_chats_limit_premium »/dialog_filters_chats_limit_default »

The maximum number of chats a Premium/non-Premium user may add to a folder (integer)

###### double_limits__dialogs_pinned

Config keys: dialogs_pinned_limit_premium »/dialogs_pinned_limit_default »

The maximum number of chats a Premium/non-Premium user may pin (integer)

###### double_limits__dialogs_folder_pinned

Config keys: dialogs_folder_pinned_limit_premium »/dialogs_folder_pinned_limit_default »

The maximum number of chats a Premium/non-Premium user may pin in a folder (integer)

###### double_limits__channels_public

Config keys: channels_public_limit_premium »/channels_public_limit_default »

The maximum number of public channels or supergroups a Premium/non-Premium user may create (integer)

###### double_limits__caption_length

Config keys: caption_length_limit_premium »/caption_length_limit_default »

The maximum UTF-8 length of media captions sendable by Premium/non-Premium users (integer)

###### double_limits__about_length

Config keys: about_length_limit_premium »/about_length_limit_default »

The maximum UTF-8 length of bios of Premium/non-Premium users (integer)

###### double_limits__chatlist_invites

Config keys: chatlist_invites_limit_premium »/chatlist_invites_limit_default »

Maximum number of per-folder chat folder deep links » that can be created by Premium/non-Premium users. (integer)

###### double_limits__chatlists_joined

Config keys: chatlists_joined_limit_premium »/chatlists_joined_limit_default »

Maximum number of shareable folders Premium/non-Premium users may have. (integer)

###### double_limits__story_expiring

Config keys: story_expiring_limit_premium »/story_expiring_limit_default »

The maximum number of active stories for Premium/non-Premium users (integer).

###### double_limits__story_caption_length

Config keys: story_caption_length_limit_premium »/story_caption_length_limit_default »

The maximum UTF-8 length of story captions for Premium/non-Premium users. (integer)

###### double_limits__stories_sent_weekly

Config keys: stories_sent_weekly_limit_premium »/stories_sent_weekly_limit_default »

Maximum number of stories that can be sent in a week by Premium/non-Premium users. (integer)

###### double_limits__stories_sent_monthly

Config keys: stories_sent_monthly_limit_premium »/stories_sent_monthly_limit_default »

Maximum number of stories that can be sent in a month by Premium/non-Premium users. (integer)

###### double_limits__stories_suggested_reactions

Config keys: stories_suggested_reactions_limit_premium »/stories_suggested_reactions_limit_default »

Maximum number of story reaction media areas » that can be added to a story by Premium/non-Premium users. (integer)

###### double_limits__recommended_channels

Config keys: recommended_channels_limit_premium »/recommended_channels_limit_default »

The maximum number of similar channels that can be recommended by channels.getChannelRecommendations» to Premium/non-Premium users. (integer)

###### double_limits__saved_dialogs_pinned

Config keys: saved_dialogs_pinned_limit_premium »/saved_dialogs_pinned_limit_default »

Maximum number of pinned dialogs in saved messages for Premium/non-Premium users.  (integer)

##### business

Premium users currently have access to Telegram Business features ».

##### last_seen

Premium users can view the last seen and message read times of other users even they can't view the last seen or read time for the current user.

##### message_privacy

Premium users can disallow incoming voice and video note messages in private chats using inputPrivacyKeyVoiceMessages and restrict incoming messages from non-contacts.

##### more_upload

Premium users can upload bigger files, as specified by the upload_max_fileparts_default vs upload_max_fileparts_premium config keys.

##### faster_download

Premium users have no download speed limits (i.e. they can't receive FLOOD_PREMIUM_WAIT_X errors when downloading files, see here » for more info).

##### wallpapers

Premium users can set custom chat wallpapers both for them and the other user in the chat.

##### peer_colors

Premium users can choose a custom color and background emoji for their profile background and messages.

##### voice_to_text

Premium users can transcribe voice messages without limits.

##### translations

Premium users can enable real-time chat translation.

##### no_ads

Premium users see no sponsored messages.

##### unique_reactions

Premium users have access to more message reactions.

##### premium_stickers

Premium users have access to premium stickersets.

##### animated_emoji

Premium users can send custom animated emojis.

##### advanced_chat_management

Premium users can reorder the default folder, auto-archive and hide new chats from non-contacts.

##### profile_badge

Premium users have a badge next to their name, showing that they are helping support Telegram.

##### animated_userpics

Animated profile pictures of Premium users will play in-chat and when browsing the dialog list.

##### app_icons

Premium users can change the default icon of the Telegram app.

##### infinite_reactions

Premium users can use custom emojis when reacting to messages.

##### emoji_status

Premium users can set a status emoji.

##### saved_tags

Premium users can use saved message tags.

##### effects

Premium users can use message effects.

##### channel_boost

Premium users can boost chats and channels.

##### forum_topic_icon

Premium users can set a custom emoji as a forum topic icon

##### todo

Premium users can post todo lists »

#### Badge

Users with a Telegram Premium subscription (user.premium is set) should have a Telegram Premium badge next to their name.

#### Animated profile pictures

The animated profile pictures of Premium users should play inside of chats and dialog lists, and not just when opening the profile page.

#### Sticker suggestions

The suggested sticker selection logic is slightly different for Premium users, see here for more info ».

### Subscribing to Telegram Premium

Here's how to activate a Telegram Premium subscription, when the user clicks on the subscribe button:

- If the premium_bot_username field is set, call messages.startBot, specifying the following parameters:

- peer and bot: The bot mentioned in premium_bot_username

- start_param: One of the following values:

- If the user clicks on the subscribe button when viewing the promo page for a specific Premium feature, provide the feature identifier (or an empty string if opened from the main promo page).

- If the user clicks on the subscribe button when viewing the promo page for a specific Telegram Business feature, provide the business feature identifier (or business if opened from the main business promo page).

- If the user clicks on the subscribe button after hitting a limit that Telegram Premium raises, provide one of the limit identifiers

- If the user clicks on the subscribe button after hitting a story-related limit that Telegram Premium raises, provide one of the story feature identifiers

- If the user clicks on the subscribe button from the Telegram Premium button in the settings, provide settings

- If the user clicks on the subscribe button from the Telegram Premium star in a profile page, provide profile

- If the user opened a premium referrer link, provide deeplink if the referrer is empty, and deeplink_$referrer if non-empty.

- Then, when the user clicks on the subscribe button in the sent invoice, follow the usual payment flow for message invoices.

- Otherwise, if the premium_invoice_slug field is set, handle the payment as you would handle a t.me/$premium_invoice_slug invoice deep link.

There is also a store-based subscription flow based on payments.assignAppStoreTransaction/payments.assignPlayMarketTransaction, but it's currently not available to third-party apps (unlike the flow described above, which can be used by all clients).

### Gifting Telegram Premium

Note: to gift a Premium subscriptions to multiple friends, the alternative payment flow described here » (inputStorePaymentPremiumGiftCode without setting boost_peer) must be used, instead.

```
premiumGiftCodeOption#257e962b flags:# users:int months:int store_product:flags.0?string store_quantity:flags.1?int currency:string amount:long = PremiumGiftCodeOption;

inputInvoicePremiumGiftStars#dabab2ef flags:# user_id:InputUser months:int message:flags.0?TextWithEntities = InputInvoice;

messageActionGiftPremium#6c6274fa flags:# currency:string amount:long months:int crypto_currency:flags.0?string crypto_amount:flags.0?long message:flags.1?TextWithEntities = MessageAction;

inputStickerSetPremiumGifts#c88b3b02 = InputStickerSet;

---functions---

payments.getPremiumGiftCodeOptions#2757ba54 flags:# boost_peer:flags.0?InputPeer = Vector<PremiumGiftCodeOption>;
```

If the other user in a private chat doesn't have a Premium subscription, we can gift them a non-recurring Telegram Premium subscription.

If the userFull.display_gifts_button flag of both us and another user is set (changed through globalPrivacySettings), a gift button should always be displayed in the text field in private chats with the other user: once clicked, the gift UI should be displayed, offering the user options to gift Telegram Premium » subscriptions or Telegram Gifts ».

The same gifting UI should always be (unconditionally) available through a chat picker, activated by a "Send a Gift" entry in the app's settings.

Users may disallow the reception of specific gift types by populating the globalPrivacySettings.disallowed_gifts flag, visible to other users in userFull.disallowed_gifts.

To obtain available gift options for Telegram Premium, invoke payments.getPremiumGiftCodeOptions.

The returned premiumGiftCodeOption constructors are an ordered list of Premium gift offers with discounts over the base price, according to the subscription duration.

Filter out only options where users == 1 (options where users > 1 are used for giveaways).

Each users/months combo can have up to two options: one in the user's native currency, and the other (optionally) in Telegram Stars (currency == "XTR").

Unofficial clients should display and use only the options where currency=XTR.

To gift a Telegram Premium subscription paying with Telegram Stars, create an inputInvoicePremiumGiftStars, then follow the usual payment flow ».

Once the payment is successfully processed, the user to which the gift was sent will automatically receive a messageService from the user that sent the gift, containing a messageActionGiftPremium constructor with further info about the price and duration of the gifted Telegram Premium subscription.
Clients should display this message, along with a sticker from the inputStickerSetPremiumGifts stickerset: here's an example.

Note that if the premium_gift_attach_menu_icon app configuration parameter is true, a gift icon should be shown in the attachment menu in private chats with users, offering the current user to gift a Telegram Premium subscription to the other user in the chat.

If the premium_gift_text_field_icon parameter is also set, a gift icon should be shown in the text bar in private chats with users (ie like the / icon in chats with bots), offering the current user to gift a Telegram Premium subscription to the other user in the chat. Can only be true if premium_gift_attach_menu_icon is also true.

Note that even if the premium_gifts field is not set, we can still gift one (or more!) Premium subscriptions using the alternative payment flow described here » (inputStorePaymentPremiumGiftCode without setting boost_peer).

Gifting a Telegram Premium subscription to another user will create boosts_per_sent_gift boost slots » for us, and one boost slot for the destination user.

### Blocked Telegram Premium

If the premium_purchase_blocked app configuration parameter is set, the user can't purchase a Premium account, and all Telegram Premium features must be hidden (like the badges of Premium users, Telegram Premium purchase buttons, and so on).

