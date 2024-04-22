# Client configuration

The MTProto API has multiple configuration parameters that can be fetched with the appropriate methods.

### MTProto configuration

The huge config constructor contains lots of useful information, from chat and message size limitations, to privacy settings, online status refresh interval and timeout, VoIP configuration, default inline bot usernames for GIF, image and venue lookup, and lots of other global and user-specific information, check out the constructor page for more information.

### Client configuration

The help.getAppConfig method returns a JSON object containing rapidly evolving, client-specific configuration parameters.
While help.getConfig returns MTProto-specific configuration with information about server-side limitations and other MTProto-related information, help.getAppConfig returns configuration parameters useful for graphical Telegram clients.

When first invoking help.getAppConfig, pass 0 to hash; in future calls, use the hash contained in the previously returned help.appConfig; if the configuration hasn't changed, a help.appConfigNotModified will be returned instead of help.appConfig.

Example value of help.appConfig.config:

Typical fields included in the resulting JSON object are:

#### emojies_animated_zoom

Animated emojis and animated dice should be scaled by this factor before being shown to the user (float)

#### keep_alive_service

Whether app clients should start a keepalive service to keep the app running and fetch updates even when the app is closed (boolean)

#### background_connection

Whether app clients should start a background TCP connection for MTProto update fetching (boolean)

#### emojies_send_dice

A list of supported animated dice stickers (array of strings).

#### emojies_send_dice_success

For animated dice emojis other than the basic , indicates the winning dice value and the final frame of the animated sticker, at which to show the fireworks  (object with emoji keys and object values, containing value and frame_start float values)

#### emojies_sounds

A map of soundbites to be played when the user clicks on the specified animated emoji; the file reference field should be base64-decoded before downloading the file (map of file IDs (inputDocument.id), with emoji string keys)

#### gif_search_branding

Specifies the name of the service providing GIF search through gif_search_username (string)

#### gif_search_emojies

Specifies a list of emojis that should be suggested as search term in a bar above the GIF search box (array of string emojis)

#### stickers_emoji_suggest_only_api

Specifies that the app should not display local sticker suggestions » for emojis at all and just use the result of messages.getStickers (bool)

#### stickers_emoji_cache_time

Specifies the validity period of the local cache of messages.getStickers, also relevant when generating the pagination hash when invoking the method. (integer)

#### qr_login_camera

Whether the Settings->Devices menu should show an option to scan a QR login code (boolean)

#### qr_login_code

Whether the login screen should show a QR code login option, possibly as default login method (string, "disabled", "primary" or "secondary")

#### dialog_filters_enabled

Whether clients should show an option for managing dialog filters AKA folders (boolean)

#### dialog_filters_tooltip

Whether clients should actively show a tooltip, inviting the user to configure dialog filters AKA folders; typically this happens when the chat list is long enough to start getting cluttered. (boolean)

#### autoarchive_setting_available

Whether clients can invoke account.setGlobalPrivacySettings with globalPrivacySettings.archive_and_mute_new_noncontact_peers = boolTrue, to automatically archive and mute new incoming chats from non-contacts. (boolean)

#### pending_suggestions

Contains a list of suggestions that should be actively shown as a tooltip to the user. (Array of strings, possible values shown in the suggestions section ».

#### topics_pinned_limit

Maximum number of topics that can be pinned in a single forum. (integer)

#### telegram_antispam_user_id

The ID of the official native antispam bot, that will automatically delete spam messages if enabled as specified in the native antispam documentation ».
When fetching the admin list of a supergroup using channels.getParticipants, if native antispam functionality in the specified supergroup, the bot should be manually added to the admin list displayed to the user.  (numeric string that represents a Telegram user/bot ID, should be casted to an int64)

#### telegram_antispam_group_size_min

Minimum number of group members required to enable native antispam functionality. (integer)

#### fragment_prefixes

List of phone number prefixes for anonymous Fragment phone numbers. (array of strings).

#### hidden_members_group_size_min

Minimum number of participants required to hide the participants list of a supergroup using channels.toggleParticipantsHidden. (integer)

#### url_auth_domains

A list of domains that support automatic login with manual user confirmation, click here for more info on URL authorization ». (array of strings)

#### autologin_domains

A list of Telegram domains that support automatic login with no user confirmation, click here for more info on URL authorization ». (array of strings)

#### whitelisted_domains

A list of Telegram domains that can always be opened without additional user confirmation, when clicking on in-app links where the URL is not fully displayed (i.e. messageEntityTextUrl entities). (array of strings)

Note that when opening direct Mini App links for the first time, confirmation should still be requested from the user, even if the domain of the containing deep link is whitelisted (i.e. t.me/<bot_username>/<short_name>?startapp=<start_parameter>, where t.me is whitelisted).

Confirmation should always be asked, even if we already opened the direct Mini App before, if the link is not visible (i.e. messageEntityTextUrl text links, inline buttons etc.).

#### round_video_encoding

Contains a set of recommended codec parameters for round videos.  (object, as described in the example)

#### chat_read_mark_size_threshold

Per-user read receipts, fetchable using messages.getMessageReadParticipants, will be available in groups with an amount of participants less or equal to chat_read_mark_size_threshold. (integer)

#### chat_read_mark_expire_period

To protect user privacy, read receipts for chats are only stored for chat_read_mark_expire_period seconds after the message was sent. (integer)

#### pm_read_date_expire_period

To protect user privacy, read receipts for private chats are only stored for pm_read_date_expire_period seconds after the message was sent. (integer)

#### groupcall_video_participants_max

Maximum number of participants in a group call (livestreams allow ∞ participants) (integer)

#### reactions_uniq_max

Maximum number of unique reactions for any given message: for example, if there are 2000  and 1000 custom emoji  reactions and reactions_uniq_max = 2, you can't add a  reaction, because that would raise the number of unique reactions to 3 > 2. (integer)

#### reactions_in_chat_max

Maximum number of reactions that can be marked as allowed in a chat using chatReactionsSome. (integer)

#### reactions_user_max_default

Maximum number of reactions that can be added to a single message by a non-Premium user. (integer)

#### reactions_user_max_premium

Maximum number of reactions that can be added to a single message by a Premium user. (integer)

#### default_emoji_statuses_stickerset_id

Default emoji status stickerset ID. (integer)
Note that the stickerset can be fetched using inputStickerSetEmojiDefaultStatuses.

#### ringtone_duration_max

The maximum duration in seconds of uploadable notification sounds » (integer)

#### ringtone_size_max

The maximum post-conversion size in bytes of uploadable notification sounds »

#### ringtone_saved_count_max

The maximum number of saveable notification sounds »

#### message_animated_emoji_max

The maximum number of custom emojis that may be present in a message. (integer)

#### stickers_premium_by_emoji_num

Defines how many Premium stickers to show in the sticker suggestion popup when entering an emoji into the text field, see the sticker docs for more info (integer, defaults to 0)

#### stickers_normal_by_emoji_per_premium_num

For Premium users, used to define the suggested sticker list, see the sticker docs for more info (integer, defaults to 2)

#### premium_purchase_blocked

The user can't purchase Telegram Premium. The app must also hide all Premium features, including stars for other users, et cetera. (boolean)

#### channels_limit_default

The maximum number of channels and supergroups a non-Premium user may join (integer)

#### channels_limit_premium

The maximum number of channels and supergroups a Premium user may join (integer)

#### saved_gifs_limit_default

The maximum number of GIFs a non-Premium user may save (integer)

#### saved_gifs_limit_premium

The maximum number of GIFs a Premium user may save (integer)

#### stickers_faved_limit_default

The maximum number of stickers a non-Premium user may add to Favorites » (integer)

#### stickers_faved_limit_premium

The maximum number of stickers a Premium user may add to Favorites » (integer)

#### dialog_filters_limit_default

The maximum number of folders a non-Premium user may create (integer)

#### dialog_filters_limit_premium

The maximum number of folders a Premium user may create (integer)

#### dialog_filters_chats_limit_default

The maximum number of chats a non-Premium user may add to a folder (integer)

#### dialog_filters_chats_limit_premium

The maximum number of chats a Premium user may add to a folder (integer)

#### dialogs_pinned_limit_default

The maximum number of chats a non-Premium user may pin (integer)

#### dialogs_pinned_limit_premium

The maximum number of chats a Premium user may pin (integer)

#### dialogs_folder_pinned_limit_default

The maximum number of chats a non-Premium user may pin in a folder (integer)

#### dialogs_folder_pinned_limit_premium

The maximum number of chats a Premium user may pin in a folder (integer)

#### channels_public_limit_default

The maximum number of public channels or supergroups a non-Premium user may create (integer)

#### channels_public_limit_premium

The maximum number of public channels or supergroups a Premium user may create (integer)

#### caption_length_limit_default

The maximum UTF-8 length of media captions sendable by non-Premium users (integer)

#### caption_length_limit_premium

The maximum UTF-8 length of media captions sendable by Premium users (integer)

#### upload_max_fileparts_default

The maximum number of file parts uploadable by non-Premium users (integer, the maximum file size can be extrapolated by multiplying this value by 524288, the biggest possible chunk size)

#### upload_max_fileparts_premium

The maximum number of file parts uploadable by Premium users (integer, the maximum file size can be extrapolated by multiplying this value by 524288, the biggest possible chunk size)

#### about_length_limit_default

The maximum UTF-8 length of bios of non-Premium users (integer)

#### about_length_limit_premium

The maximum UTF-8 length of bios of Premium users (integer)

#### premium_promo_order

Array of string identifiers, indicating the order of Telegram Premium features in the Telegram Premium promotion popup, see here for the possible values »

#### premium_bot_username

Contains the username of the official Telegram Premium bot that may be used to buy a Telegram Premium subscription, see here for detailed instructions » (string)

#### premium_invoice_slug

Contains an invoice slug that may be used to buy a Telegram Premium subscription, see here for detailed instructions » (string)

#### premium_gift_attach_menu_icon

Whether a gift icon should be shown in the attachment menu in private chats with users, offering the current user to gift a Telegram Premium subscription to the other user in the chat. (boolean)

#### premium_gift_text_field_icon

Whether a gift icon should be shown in the text bar in private chats with users (ie like the / icon in chats with bots), offering the current user to gift a Telegram Premium subscription to the other user in the chat. Can only be true if premium_gift_attach_menu_icon is also true. (boolean)

#### chatlist_update_period

Users that import a folder using a chat folder deep link » should retrieve additions made to the folder by invoking chatlists.getChatlistUpdates at most every chatlist_update_period seconds. (integer)

#### chatlist_invites_limit_default

Maximum number of per-folder chat folder deep links » that can be created by non-Premium users. (integer)

#### chatlist_invites_limit_premium

Maximum number of per-folder chat folder deep links » that can be created by Premium users. (integer)

#### chatlists_joined_limit_default

Maximum number of shareable folders non-Premium users may have. (integer)

#### chatlists_joined_limit_premium

Maximum number of shareable folders Premium users may have. (integer)

#### small_queue_max_active_operations_count

A soft limit, specifying the maximum number of files that should be downloaded in parallel from the same DC, for files smaller than 20MB. (integer)

#### large_queue_max_active_operations_count

A soft limit, specifying the maximum number of files that should be downloaded in parallel from the same DC, for files bigger than 20MB. (integer)

#### authorization_autoconfirm_period

An unconfirmed session » will be autoconfirmed this many seconds after login. (integer)

#### story_viewers_expire_period

The exact list of users that viewed the story will be hidden from the poster this many seconds after the story expires. (integer)

This limit applies only to non-Premium users, Premium users can always access the viewer list.

#### story_expiring_limit_default

The maximum number of active stories for non-Premium users (integer).

#### story_expiring_limit_premium

The maximum number of active stories for Premium users (integer).

#### story_caption_length_limit_premium

The maximum UTF-8 length of story captions for Premium users. (integer)

#### story_caption_length_limit_default

The maximum UTF-8 length of story captions for non-Premium users. (integer)

#### stories_posting

Indicates whether users can post stories. (string)

One of:

- enabled - Any user can post stories.

- premium - Only users with a Premium subscription can post stories.

- disabled - Users can't post stories.

#### stories_stealth_past_period

Enabling stories stealth mode with the past flag will erase views of any story opened in the past stories_stealth_past_period seconds. (integer)

#### stories_stealth_future_period

Enabling stories stealth mode with the future flag will hide views of any story opened in the next stories_stealth_future_period seconds. (integer)

#### stories_stealth_cooldown_period

After enabling stories stealth mode, this many seconds must elapse before the user is allowed to enable it again. (integer)

#### stories_sent_weekly_limit_default

Maximum number of stories that can be sent in a week by non-Premium users. (integer)

#### stories_sent_weekly_limit_premium

Maximum number of stories that can be sent in a week by Premium users. (integer)

#### stories_sent_monthly_limit_default

Maximum number of stories that can be sent in a month by non-Premium users. (integer)

#### stories_sent_monthly_limit_premium

Maximum number of stories that can be sent in a month by Premium users. (integer)

#### stories_suggested_reactions_limit_default

Maximum number of story reaction media areas » that can be added to a story by non-Premium users. (integer)

#### stories_suggested_reactions_limit_premium

Maximum number of story reaction media areas » that can be added to a story by Premium users. (integer)

#### stories_venue_search_username

Username of the inline bot to use to generate venue location tags for stories, see here » for more info. (string)

#### stories_changelog_user_id

ID of the official Telegram user that will post stories about new Telegram features: stories posted by this user should be shown on the active or active and hidden stories bar just like for contacts, even if the user was removed from the contact list. (integer, defaults to 777000)

#### stories_entities

Whether styled text entities and links in story text captions can be used by all users (enabled), only [Premium](/api/premium users) (premium), or no one (disabled). (string)

This field is used both when posting stories, to indicate to the user whether they can use entities, and when viewing stories, to hide entities (client-side) on stories posted by users whose Premium subscription has expired (if stories_entities == "premium" and user.premium is not set, or if stories_entities == "disabled").

#### giveaway_gifts_purchase_available

Whether giveaways can be started by the current user. (boolean)

#### giveaway_add_peers_max

The maximum number of users that can be specified when making a direct giveaway. (integer)

#### giveaway_countries_max

The maximum number of countries that can be specified when restricting the set of participating countries in a giveaway.  (itneger)

#### giveaway_boosts_per_premium

The number of boosts that will be gained by a channel for each winner of a giveaway. (integer)

#### giveaway_period_max

The maximum duration in seconds of a giveaway. (integer)

#### boosts_channel_level_max

Maximum boost level for channels. (integer)

#### boosts_per_sent_gift

The number of additional boost slots that the current user will receive when gifting a Telegram Premium subscription.

#### transcribe_audio_trial_weekly_number

The maximum number of speech recognition » calls per week for non-Premium users. (integer)

#### transcribe_audio_trial_duration_max

The maximum allowed duration of media in seconds for speech recognition » for non-Premium users. (integer)

#### recommended_channels_limit_default

The maximum number of similar channels that can be recommended by channels.getChannelRecommendations» to non-Premium users. (integer)

#### recommended_channels_limit_premium

The maximum number of similar channels that can be recommended by channels.getChannelRecommendations» to Premium users. (integer)

#### quote_length_max

Maximum UTF-8 length of quoted text. (integer)

#### channel_bg_icon_level_min

After reaching at least this boost level », channels gain the ability to change their message accent palette emoji ».  (integer)

#### channel_profile_bg_icon_level_min

After reaching at least this boost level », channels gain the ability to change their profile accent palette emoji ».  (integer)

#### channel_emoji_status_level_min

After reaching at least this boost level », channels gain the ability to change their status emoji ».  (integer)

#### channel_wallpaper_level_min

After reaching at least this boost level », channels gain the ability to set a fill channel wallpaper, see here » for more info.  (integer)

#### channel_custom_wallpaper_level_min

After reaching at least this boost level », channels gain the ability to set any custom wallpaper, not just fill channel wallpapers, see here » for more info.  (integer)

#### saved_dialogs_pinned_limit_default

Maximum number of pinned dialogs in saved messages for non-Premium users.  (integer)

#### saved_dialogs_pinned_limit_premium

Maximum number of pinned dialogs in saved messages for Premium users.  (integer)

### Suggestions

The API can return a set of useful suggestions for users of graphical clients.

#### Basic suggestions

The help.getAppConfig method returns a JSON object containing rapidly evolving, client-specific configuration parameters.
A full list of these parameters can be seen in the Client Configuration section », but we're mostly interested in the pending_suggestions and autoarchive_setting_available fields of the returned JSON object:

- autoarchive_setting_available - Whether clients can invoke account.setGlobalPrivacySettings with globalPrivacySettings.archive_and_mute_new_noncontact_peers = boolTrue, to automatically archive and mute new incoming chats from non-contacts. (boolean)

- pending_suggestions - Contains a list of suggestions that should be actively shown as a tooltip to the user. Array of strings, possible values shown below:

- "AUTOARCHIVE_POPULAR" - Users should invoke account.setGlobalPrivacySettings with globalPrivacySettings.archive_and_mute_new_noncontact_peers = boolTrue, to automatically archive and mute new incoming chats from non-contacts.

- "VALIDATE_PASSWORD" - Users should make sure they still remember their 2-step verification password.

- "VALIDATE_PHONE_NUMBER" - Users should check whether their authorization phone number is correct and change the phone number if it is inaccessible.

- "NEWCOMER_TICKS" - Show the user a hint about the meaning of one and two ticks on sent messages.

- "SETUP_PASSWORD" - Show the user a hint, asking them to check whether they still remember their 2FA password

- "PREMIUM_ANNUAL" - Suggests the user to subscribe to the Premium subscription (with annual payments)

- "PREMIUM_UPGRADE" - Suggests the user to upgrade their existing Premium subscription from monthly payments to annual payments

- "PREMIUM_RESTORE" - Suggests the user to restore a recently expired Premium subscription

#### Channel suggestions

Some channel/supergroup-related suggestions can also be contained in the pending_suggestions field of the channelFull constructor, returned by channels.getFullChannel.
Here's a list of possible suggestions:

- CONVERT_GIGAGROUP - The supergroup has many participants: the admin should call channels.convertToGigagroup to convert it to a gigagroup.

#### Dismissing suggestions

help.dismissSuggestion can be used to dismiss a suggestion.
Pass inputPeerEmpty to peer for basic suggestions and the channel/supergroup's peer for channel suggestions.

### App-specific configuration

- help.getAppUpdate - Get info about an application update, can contain the updated application binary in the attached document

- help.getInviteText - Returns a localized invitation message that can be sent via SMS to contacts that haven't signed up to Telegram yet

### Terms of service

These methods can be used for managing consent to Telegram's Terms Of Service.

Typically, before a user signs up by invoking auth.signUp, apps should show a pop-up (if the popup flag of the help.termsOfService method is set), asking the user to accept Telegram's terms of service; in case of denial, the user is to be returned to the initial page of the login flow.

When signing up for the first time, the help.termsOfService is to be obtained from the auth.authorizationSignUpRequired constructor returned by the auth.signIn.

After signing up, or when logging in as an existing user, apps are supposed to call help.getTermsOfServiceUpdate to check for any updates to the Terms of Service; this call should be repeated after expires seconds have elapsed.
If an update to the Terms Of Service is available, clients are supposed to show a consent popup; if accepted, clients should call help.acceptTermsOfService, providing the termsOfService id JSON object; in case of denial, clients are to delete the account using account.deleteAccount, providing Decline ToS update as deletion reason.

Example implementation: android (signup), android (after login)

### Telegram support info

These methods can be used for fetching info about Telegram's support user, that users can use to get support and ask questions about the app.

- help.getSupport - Will return the user object that can be used for contacting support.

- help.getSupportName - Will return a localized name for the support chat.

### Country information and login phone patterns

help.getCountriesList can be used to fetch a list of localized names for all available countries and phone code patterns for logging in.

The phone code pattern should be used when showing the login screen, or when changing phone number: for example, a pattern value of XXX XXX XXX with country_code +39 indicates that the phone field for login should accept a spaced pattern like +39 123 456 789.
Also, the beginning of the national part of the phone number (123 456 789) should match one of the prefixes, if any were returned.

Additionally, the fragment_prefixes client configuration parameter contains a list of phone number prefixes for anonymous Fragment phone numbers.

