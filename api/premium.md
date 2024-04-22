# Telegram Premium
Telegram Premium is an optional subscription service that unlocks additional exclusive client-side and API-side features, while helping support the development of the app. It is a part of Telegram’s sustainable monetization – driven by our users, rather than advertisers or shareholders. This way, Telegram can remain independent and prioritize its users first.
> This page describes how should client apps handle Premium features: for a user-friendly overview of Telegram Premium features, see the Telegram Premium FAQ.
### Telegram Premium users
Premium users will have the premium flag of the user set.
Use users.getUsers with inputUserSelf to fetch info about the current subscription status of the current user.
You can also directly use help.getPremiumPromo, as it will return info about the current user in the users field.
### Telegram Premium features
Telegram Premium offers a set of additional features and raised limits: clients should be aware of the current subscription status to accordingly modify client behavior.
#### Promo page
Clients should show a Telegram Premium button in the settings.
Clicking on this button in the settings, clicking on the badge of a Premium user or hitting one of the Premium limits listed below should open a Telegram Premium modal.
Call help.getPremiumPromo and help.getAppConfig to fetch info on how to build the premium modal.
help.getAppConfig will return a list of Premium feature identifiers in the premium_promo_order appConfig field: the modal should contain a row for each returned feature, ordered as specified in the returned array.
Possible feature identifiers:
- stories - Premium users have various Story-related improvements:
- Stories posted by Premium users are shown first to users when fetching the list of active stories with stories.getAllStories ».
- Premium users can activate stealth mode »
- Premium users can fetch the full viewer list of stories, even after they expire »
- Premium users can set custom expiration options when posting stories »
- Premium users can post stories with longer captions, as specified by the story_caption_length_limit_* » config keys.
- Premium users can add more story reaction media areas » to a story, as specified by the stories_suggested_reactions_limit_* » config keys.
- Premium users can styled text entities and links in story captions, as specified by the stories_entities » config key.
- Premium users can download non-protected stories.
- See the stories documentation » for more information on stories.
- double_limits - Clicking on this entry should open a secondary popup with a list of the improved Premium limits ».
- more_upload - Premium users can upload bigger files, as specified by the upload_max_fileparts_default vs upload_max_fileparts_premium config keys.
- faster_download - Premium users have no download speed limits.
- wallpapers - Premium users can set custom chat wallpapers both for them and the other user in the chat.
- peer_colors - Premium users can choose a custom color and background emoji for their profile background and messages.
- voice_to_text - Premium users can transcribe voice messages without limits.
- translations - Premium users can enable real-time chat translation.
- no_ads - Premium users see no sponsored messages.
- unique_reactions - Premium users have access to more message reactions.
- premium_stickers - Premium users have access to premium stickersets.
- animated_emoji - Premium users can send custom animated emojis.
- advanced_chat_management - Premium users can reorder the default folder, auto-archive and hide new chats from non-contacts.
- profile_badge - Premium users have a badge next to their name, showing that they are helping support Telegram.
- animated_userpics - Animated profile pictures of Premium users will play in-chat and when browsing the dialog list.
- app_icons - Premium users can change the default icon of the Telegram app.
- infinite_reactions - Premium users can use custom emojis when reacting to messages.
- emoji_status - Premium users can set a status emoji.
The help.premiumPromo constructor returned by help.getPremiumPromo contains various info about the subscription, as described in the constructor page.
#### Premium limits
What follows is a list of appConfig integer config parameters.
Note that whenever config keys end with a * in the following list, the * should be replaced with premium or default, to fetch the appropriate limit value for Premium and non-Premium users.
- reactions_user_max_* - The maximum number of reactions that can be added to a single message by the user.
- channels_limit_* - The maximum number of channels and supergroups a user may join.
- saved_gifs_limit_* - The maximum number of GIFs a user may save.
- stickers_faved_limit_* - The maximum number of stickers a user may add to favorites.
- dialog_filters_limit_* - The maximum number of folders a user may create.
- dialog_filters_chats_* - The maximum number of chats a user may add to a folder.
- dialogs_pinned_limit_* - The maximum number of chats a user may pin.
- dialogs_folder_pinned_limit_* - The maximum number of chats a user may pin in a folder.
- channels_public_limit_* - The maximum number of public channels or supergroups a user may create.
- caption_length_limit_* - The maximum UTF-8 length of media captions.
- about_length_limit_* - The maximum UTF-8 length of user bios.
- chatlist_invites_limit_* - Maximum number of per-folder chat folder deep links » that can be created.
- chatlists_joined_limit_* - Maximum number of shareable folders a user may have.
- recommended_channels_limit_* - The maximum number of similar channels that can be recommended by channels.getChannelRecommendations» to users.
- saved_dialogs_pinned_limit_* - Maximum number of pinned dialogs in saved messages.
#### Badge
Users with a Telegram Premium subscription (user.premium is set) should have a Telegram Premium badge next to their name.
#### Animated profile pictures
The animated profile pictures of Premium users should play inside of chats and dialog lists, and not just when opening the profile page.
#### Sticker suggestions
The suggested sticker selection logic is slightly different for Premium users, see here for more info ».
### Subscribing to Telegram Premium
Here's how to activate a Telegram Premium subscription, when the user clicks on the subscribe button:
- If the premium_bot_username field is set, call messages.startBot, specifying the following parameters:
- peer and bot: The bot mentioned in premium_bot_username
- start_param: One of the following values:
- If the user clicks on the subscribe button when viewing the promo page for a specific Premium feature, provide the feature identifier.
- If the user clicks on the subscribe button after hitting a limit that Telegram Premium raises, provide double_limits
- If the user clicks on the subscribe button from the Telegram Premium button in the settings, provide settings
- If the user clicks on the subscribe button from the Telegram Premium star in a profile page, provide profile
- Then, when the user clicks on the subscribe button in the sent invoice, follow the usual payment flow for message invoices.
- Otherwise, if the premium_invoice_slug field is set, handle the payment as you would handle a t.me/$premium_invoice_slug invoice deep link.
There is also a store-based subscription flow based on payments.assignAppStoreTransaction/payments.assignPlayMarketTransaction, but it's currently not available to third-party apps (unlike the flow described above, which can be used by all clients).
### Gifting Telegram Premium
Note: to gift a Premium subscriptions to multiple friends, the alternative payment flow described here » (inputStorePaymentPremiumGiftCode without setting boost_peer) should be used, instead.
If after calling users.getFullUser the resulting userFull constructor has one or more premiumGiftOptions in the premium_gifts field, we can gift a non-recurring Telegram Premium subscription to this user.
The premiumGiftOption constructors contain an ordered list of Premium gift offers with discounts over the base price, according to the subscription duration: to process the gift payment open the deep link contained in the bot_url field.
Once the payment is successfully processed, the user to which the gift was sent will automatically receive a messageService from the user that sent the gift, containing a messageActionGiftPremium constructor with further info about the price and duration of the gifted Telegram Premium subscription.
Clients should display this message, along with a sticker from the inputStickerSetPremiumGifts stickerset: here's an example.
Note that if the premium_gift_attach_menu_icon app configuration parameter is true, a gift icon should be shown in the attachment menu in private chats with users, offering the current user to gift a Telegram Premium subscription to the other user in the chat.
If the premium_gift_text_field_icon parameter is also set, a gift icon should be shown in the text bar in private chats with users (ie like the / icon in chats with bots), offering the current user to gift a Telegram Premium subscription to the other user in the chat. Can only be true if premium_gift_attach_menu_icon is also true.
Note that even if the premium_gifts field is not set, we can still gift one (or more!) Premium subscriptions using the alternative payment flow described here » (inputStorePaymentPremiumGiftCode without setting boost_peer).
Gifting a Telegram Premium subscription to another user will create boosts_per_sent_gift boost slots » for us, and one boost slot for the destination user.
### Blocked Telegram Premium
If the premium_purchase_blocked app configuration parameter is set, the user can't purchase a Premium account, and all Telegram Premium features must be hidden (like the badges of Premium users, Telegram Premium purchase buttons, and so on).
