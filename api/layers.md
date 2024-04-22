# Layers

Below you will find information on schema changes. For more details on the use of layers, see Invoking API methods.

### Layer 170

To view all the changes since the last update, start reading the changelog @ Layer 159.

Most importantly, the following detailed articles were added:

- Working with stories »

- Working with boosts »

- Working with giveaways »

- Working with accent colors »

- Working with the recommendation system »

- Working with the action bar »

- Working with contacts »

- Working with the blocklist »

- Working with geochats »

- Working with privacy settings »

- Working with the takeout API »

- Working with saved messages »

Also added documentation for streamed uploads and improved the docs for method queue, quick ACKs and content-related messages.

The RPC error database » was also updated.

The following new deep links were added:

- Story links »

- Boost links »

- Direct mini app links »

- Premium giftcode links »

- Premium multigift links »

This layer introduces the saved messages dialog list and several other saved messages improvements »!

#### Schema changes

##### New Methods

- Added messages.getSavedDialogs - Returns the current saved dialog list, see here » for more info.

- Added messages.getSavedHistory - Returns saved messages » forwarded from a specific peer

- Added messages.deleteSavedHistory - Deletes messages forwarded from a specific peer to saved messages ».

- Added messages.getPinnedSavedDialogs - Get pinned saved dialogs, see here » for more info.

- Added messages.toggleSavedDialogPin - Pin or unpin a saved message dialog ».

- Added messages.reorderPinnedSavedDialogs - Reorder pinned saved message dialogs ».

##### Changed Methods

- Added saved_peer_id parameter in messages.search

- Added saved_peer_id parameter in messages.getSearchCounters

- Added flags, saved_peer_id parameters in messages.getSearchResultsCalendar

- Added flags, saved_peer_id parameters in messages.getSearchResultsPositions

##### New Constructors

- Added savedDialog - Represents a saved dialog ».

- Added updateSavedDialogPinned - A saved message dialog was pinned/unpinned

- Added updatePinnedSavedDialogs - Pinned saved dialogs » were updated

- Added messages.savedDialogs - Represents some saved message dialogs ».

- Added messages.savedDialogsSlice - Incomplete list of saved message dialogs » with messages and auxiliary data.

- Added messages.savedDialogsNotModified - The saved dialogs haven't changed

##### Changed Constructors

- Added saved_peer_id parameter in message

- Added saved_out, saved_from_id, saved_from_name, saved_date parameters in messageFwdHeader

#### Schema

### Layer 169

Allow requesting and sending more than one peer using keyboardButtonRequestPeer.

#### Schema changes

##### Changed Methods

- Added requested_peers parameter, removed requested_peer parameter in messages.sendBotRequestedPeer

##### Changed Constructors

- Added peers parameter, removed peer parameter in messageActionRequestedPeer

- Added max_quantity parameter in keyboardButtonRequestPeer

#### Schema

### Layer 168

Added support for emoji statuses, wallpapers and profile color palettes in channels, added support for custom prizes and public winners in giveaways through prize_description and winners_are_visible+messageMediaGiveawayResults, channel post embedding in stories and a new stories.getStoryReactionsList method to fetch reaction and interactions for channel stories and improved pagination in stats.getMessagePublicForwards.

Also, bots now receive events about reactions.

#### Schema changes

##### New Methods

- Added stories.getStoryReactionsList - Get the reaction and interaction list of a story posted to a channel, along with the sender of each reaction.

- Added channels.updateEmojiStatus - Set an emoji status for a channel.

- Added account.getChannelDefaultEmojiStatuses - Get a list of default suggested channel emoji statuses.

- Added account.getChannelRestrictedStatusEmojis - Returns fetch the full list of custom emoji IDs » that cannot be used in channel emoji statuses ».

##### Changed Methods

- Changed type of stats.getMessagePublicForwards from messages.Messages to stats.PublicForwards

- Added offset parameter, removed offset_rate, offset_peer, offset_id parameters in stats.getMessagePublicForwards

- Added forwards_first parameter in stories.getStoryViewsList

- Added for_profile parameter, changed type of color from int to flags.2?int in channels.updateColor

##### Deleted Methods

- Removed help.getAppChangelog

##### New Constructors

- Added messageMediaGiveawayResults - A giveaway with public winners has finished, this constructor contains info about the winners.

- Added storyReaction - How a certain peer reacted to a story

- Added storyReactionPublicForward - A certain peer has forwarded the story as a message to a public chat or channel.

- Added storyReactionPublicRepost - A certain peer has reposted the story.

- Added stories.storyReactionsList - List of peers that reacted to or intercated with a specific story

- Added storyViewPublicForward - A certain peer has forwarded the story as a message to a public chat or channel.

- Added storyViewPublicRepost - A certain peer has reposted the story.

- Added channelAdminLogEventActionChangePeerColor - The message accent color was changed

- Added channelAdminLogEventActionChangeProfilePeerColor - The profile accent color was changed

- Added channelAdminLogEventActionChangeWallpaper - The wallpaper was changed

- Added channelAdminLogEventActionChangeEmojiStatus - The emoji status was changed

- Added inputStickerSetEmojiChannelDefaultStatuses - Default custom emoji status stickerset for channel statuses

- Added mediaAreaChannelPost - Represents a channel post.

- Added inputMediaAreaChannelPost - Represents a channel post

- Added updateBotMessageReaction - Bots only: a user has changed their reactions on a message with public reactions.

- Added updateBotMessageReactions - Bots only: the number of reactions on a message with anonymous reactions has changed.

##### Changed Constructors

- Added video, round, voice parameters in messageMediaDocument

- Added channel_emoji_status parameter in stickerSet

- Added profile_color, emoji_status, level parameters in channel

- Added wallpaper parameter in channelFull

- Added emoticon parameter in wallPaperSettings

- Added views_count, forwards_count, chats parameters in stories.storyViewsList

- Added winners_are_visible, prize_description parameters in inputStorePaymentPremiumGiveaway

- Changed type of from_id from Peer to flags.4?Peer in payments.checkedGiftCode

- Added winners_are_visible, prize_description parameters in messageMediaGiveaway

- Added currency, amount, crypto_currency, crypto_amount parameters in messageActionGiftCode

- Added channel_min_level parameter in help.peerColorOption

##### Deleted Constructors

- Removed channelAdminLogEventActionChangeColor

- Removed channelAdminLogEventActionChangeBackgroundEmoji

#### Schema

### Layer 167

Added support for reposting stories, profile colors, story statistics, channel recommendations, setting a wallpaper on both sides of a chat, syncing the "View as messages" setting for forums, audio transcription for non-Premium users, improved quotes, improved sponsored messages and improved methods for custom emoji stickersets.

#### Schema changes

##### New Methods

- Added channels.toggleViewForumAsMessages - Users may also choose to display messages from all topics of a forum as if they were sent to a normal group, using a "View as messages" setting in the local client: this setting only affects the current account, and is synced to other logged in sessions using this method.

- Added messages.searchEmojiStickerSets - Search for custom emoji stickersets »

- Added channels.getChannelRecommendations - Obtain a list of similarly themed public channels, selected based on similarities in their subscriber bases.

- Added stats.getStoryStats - Get statistics for a certain story.

- Added stats.getStoryPublicForwards - Obtain forwards of a story as a message to public chats and reposts by public channels.

- Added help.getPeerColors - Get the set of accent color palettes » that can be used for message accents.

- Added help.getPeerProfileColors - Get the set of accent color palettes » that can be used in profile page backgrounds.

##### Changed Methods

- Added for_both, revert parameters in messages.setChatWallPaper

- Added fwd_modified, fwd_from_id, fwd_from_story parameters in stories.sendStory

- Added for_profile parameter, changed type of color from int to flags.2?int in account.updateColor

##### New Constructors

- Added updateChannelViewForumAsMessages - Users may also choose to display messages from all topics as if they were sent to a normal group, using a "View as messages" setting in the local client.

- Added messageActionGiveawayResults - A giveaway has ended.

- Added updatePeerWallpaper - The wallpaper » of a given peer has changed.

- Added storyFwdHeader - Contains info about the original poster of a reposted story.

- Added postInteractionCountersMessage - Interaction counters for a message.

- Added postInteractionCountersStory - Interaction counters for a story.

- Added stats.storyStats - Contains statistics about a story.

- Added publicForwardMessage - Contains info about a forward of a story as a message.

- Added publicForwardStory - Contains info about a forward of a story as a repost by a public channel.

- Added stats.publicForwards - Contains info about the forwards of a story as a message to public chats and reposts by public channels.

- Added peerColor - Represents a color palette ».

- Added help.peerColorSet - Represents a color palette that can be used in message accents ».

- Added help.peerColorProfileSet - Represents a color palette that can be used in profile pages ».

- Added help.peerColorOption - Contains info about a color palette ».

- Added help.peerColorsNotModified - The list of color palettes has not changed.

- Added help.peerColors - Contains info about multiple color palettes ».

##### Changed Constructors

- Added view_forum_as_messages parameter in dialog

- Added wallpaper_overridden parameter in userFull

- Added profile_color parameter, removed background_emoji_id parameter, changed type of color from flags2.7?int to flags2.8?PeerColor in user

- Removed background_emoji_id parameter, changed type of color from flags2.6?int to flags2.7?PeerColor in channel

- Added view_forum_as_messages parameter in channelFull

- Added reactions_per_post, views_per_story, shares_per_story, reactions_per_story, reactions_by_emotion_graph, story_interactions_graph, story_reactions_by_emotion_graph, recent_posts_interactions parameters, removed recent_message_interactions parameter in stats.broadcastStats

- Added quote_offset parameter in messageReplyHeader

- Added reactions_by_emotion_graph parameter in stats.messageStats

- Added app, button_text parameters in sponsoredMessage

- Added trial_remains_num, trial_remains_until_date parameters in messages.transcribedAudio

- Added flags, same, for_both parameters in messageActionSetChatWallPaper

- Added fwd_from parameter in storyItem

- Added quote_offset parameter in inputReplyToMessage

##### Deleted Constructors

- Removed messageInteractionCounters

- Removed messageActionSetSameChatWallPaper

#### PUSH notification changes

##### New PUSH notifications

- Added CHANNEL_MESSAGE_GIVEAWAY - {1} posted a giveaway of {2}x {3}m Premium subscriptions

- Added CHAT_MESSAGE_GIVEAWAY - {1} sent a giveaway of {3}x {4}m Premium subscriptions to the group {2}

- Added CHAT_REACT_GIVEAWAY - {1} reacted {3} in group {2} to your giveaway

- Added MESSAGE_GIFTCODE - {1} sent you a Gift Code for {2} of Telegram Premium

- Added MESSAGE_GIVEAWAY - {1} sent you a giveaway of {2}x {3}m Premium subscriptions

- Added MESSAGE_SAME_WALLPAPER - {1} set a same wallpaper for this chat

- Added MESSAGE_WALLPAPER - {1} set a new wallpaper for this chat

- Added PINNED_GIVEAWAY - {1} pinned a giveaway

- Added REACT_GIVEAWAY - {1} reacted {2} to your giveaway

#### Schema

### Layer 166

Introducing giveaways, gift code links, accent colors, quotes, improved boosts and improved webpage previews.

#### Schema changes

##### New Methods

- Added payments.getPremiumGiftCodeOptions - Obtain a list of Telegram Premium giveaway/gift code » options.

- Added payments.checkGiftCode - Obtain information about a Telegram Premium giftcode »

- Added payments.applyGiftCode - Apply a Telegram Premium giftcode »

- Added payments.getGiveawayInfo - Obtain information about a Telegram Premium giveaway ».

- Added payments.launchPrepaidGiveaway - Launch a prepaid giveaway ».

- Added account.updateColor - Update the accent color and background custom emoji » of the current account.

- Added channels.updateColor - Update the accent color and background custom emoji » of a channel.

- Added account.getDefaultBackgroundEmojis - Get a set of suggested custom emoji stickers that can be used in an accent color pattern.

- Added premium.getBoostsList - Obtains info about the boosts that were applied to a certain channel (admins only)

- Added premium.getMyBoosts - Obtain which peers are we currently boosting, and how many boost slots we have left.

- Added premium.applyBoost - Apply one or more boosts » to a peer.

- Added premium.getBoostsStatus - Gets the current number of boosts of a channel.

- Added premium.getUserBoosts - Returns the lists of boost that were applied to a channel by a specific user (admins only)

##### Changed Methods

- Added invert_media parameter in messages.sendMessage

- Added invert_media parameter in messages.sendMedia

- Added invert_media parameter in messages.editMessage

- Added invert_media parameter in messages.editInlineBotMessage

- Added invert_media, reply_to, media parameters, removed reply_to_msg_id, top_msg_id parameters in messages.saveDraft

- Changed type of messages.getWebPage from WebPage to messages.WebPage

- Added invert_media parameter in messages.sendMultiMedia

##### Deleted Methods

- Removed stories.getBoostsStatus

- Removed stories.getBoostersList

- Removed stories.canApplyBoost

- Removed stories.applyBoost

##### New Constructors

- Added messages.webPage - Represents an Instant View webpage.

- Added inputStorePaymentPremiumGiftCode - Used to gift Telegram Premium subscriptions only to some specific subscribers of a channel or to some of our contacts, see here » for more info on giveaways and gifts.

- Added inputStorePaymentPremiumGiveaway - Used to pay for a giveaway, see here » for more info.

- Added inputInvoicePremiumGiftCode - Used if the user wishes to start a channel giveaway or send some giftcodes to members of a channel, in exchange for boosts.

- Added premiumGiftCodeOption - Contains info about a giveaway/gift option.

- Added payments.checkedGiftCode - Contains info about a Telegram Premium giftcode link.

- Added messageMediaGiveaway - Contains info about a giveaway, see here » for more info.

- Added messageActionGiftCode - Contains a Telegram Premium giftcode link.

- Added messageActionGiveawayLaunch - A giveaway was started.

- Added payments.giveawayInfo - Contains info about an ongoing giveaway.

- Added payments.giveawayInfoResults - A giveaway has ended.

- Added messageEntityBlockquote - Message entity representing a block quote.

- Added prepaidGiveaway - Contains info about a prepaid giveaway ».

- Added inputMediaWebPage - Specifies options that will be used to generate the link preview for the caption, or even a standalone link preview without an attached message.

- Added inputBotInlineMessageMediaWebPage - Specifies options that will be used to generate the link preview for the message, or even a standalone link preview without an attached message.

- Added botInlineMessageMediaWebPage - Specifies options that must be used to generate the link preview for the message, or even a standalone link preview without an attached message.

- Added channelAdminLogEventActionChangeColor - The background profile color » of a channel was changed.

- Added channelAdminLogEventActionChangeBackgroundEmoji - The custom emoji used to generate the pattern of the background profile color » of a channel was changed.

- Added boost - Info about one or more boosts applied by a specific user.

- Added premium.boostsList - List of boosts that were applied to a peer by multiple users.

- Added myBoost - Contains information about a single boost slot ».

- Added premium.myBoosts - A list of peers we are currently boosting, and how many boost slots we have left.

- Added premium.boostsStatus - Contains info about the current boost status of a peer.

- Added updateBotChatBoost - A channel boost has changed (bots only)

##### Changed Constructors

- Added invert_media parameter in message

- Added invert_media parameter in updateServiceNotification

- Added flags, url parameters in webPageEmpty

- Added flags, url parameters in webPagePending

- Added has_large_media parameter in webPage

- Added flags, force_large_media, force_small_media, manual, safe parameters in messageMediaWebPage

- Added color parameter in chatInvite

- Added text_color parameter in stickerSet

- Added color, background_emoji_id parameters in user

- Added color, background_emoji_id parameters in channel

- Added invert_media parameter in inputBotInlineMessageMediaAuto

- Added invert_media parameter in inputBotInlineMessageText

- Added invert_media parameter in botInlineMessageMediaAuto

- Added invert_media parameter in botInlineMessageText

- Added invert_media, reply_to, media parameters, removed reply_to_msg_id parameter in draftMessage

- Added quote, reply_from, reply_media, quote_text, quote_entities parameters, changed type of reply_to_msg_id from int to flags.4?int in messageReplyHeader

- Added reply_to_peer_id, quote_text, quote_entities parameters in inputReplyToMessage

##### Deleted Constructors

- Removed stories.boostsStatus

- Removed stories.canApplyBoostOk

- Removed stories.canApplyBoostReplace

- Removed booster

- Removed stories.boostersList

#### Schema

### Layer 164

Introducing Telegram Stories, channel boosts, session confirmation, side menu Mini Apps, direct link Mini Apps, custom methods and multiple new events for Mini Apps and a close friends list.

A new story premium feature identifier was added.

The following new web events were also added to provide more functionality to mini apps:

- web_app_request_write_access »

- web_app_request_phone »

- web_app_invoke_custom_method »

- web_app_read_text_from_clipboard »

- web_app_open_scan_qr_popup »

- web_app_close_scan_qr_popup »

- web_app_setup_settings_button »

Also, the following changes were made to existing web events:

- web_app_open_link » events have now a 1-second inactivity TTL instead of 10 seconds, see here » for more info.

- web_app_open_link » now has an optional try_instant_view field that if set, equal to true and if the scheme of the passed url is either http or https, indicates the link should be opened in Instant View mode if possible.

#### Schema changes

##### New Methods

- Added stories.activateStealthMode - Activates stories stealth mode, see here » for more info.

- Added contacts.setBlocked - Replace the contents of an entire blocklist, see here for more info ».

- Added stories.sendReaction - React to a story.

- Added bots.canSendMessage - Check whether the specified bot can send us messages

- Added bots.allowSendMessage - Allow the specified bot to send us messages

- Added bots.invokeWebViewCustomMethod - Send a custom request from a mini bot app, triggered by a web_app_invoke_custom_method event ».

- Added stories.getPeerStories - Fetch the full active story list of a specific peer.

- Added stories.getAllReadPeerStories - Obtain the latest read story ID for all peers when first logging in, returned as a list of updateReadStories updates, see here » for more info.

- Added stories.getPeerMaxIDs - Get the IDs of the maximum read stories for a set of peers.

- Added stories.getChatsToSend - Obtain a list of channels where the user can post stories

- Added stories.togglePeerStoriesHidden - Hide the active stories of a user, preventing them from being displayed on the action bar on the homescreen, see here » for more info.

- Added stories.getBoostsStatus - Get the current boost status of a channel, see here » for more info on boosts.

- Added stories.getBoostersList - Obtain info about the users currently boosting a channel, see here » for more info about boosts.

- Added stories.canApplyBoost - Check whether a channel can be boosted, see here for more info ».

- Added stories.applyBoost - Boost » a channel, leveling it up and granting it permission to post stories ».

##### Changed Methods

- Added flags, my_stories_from parameters in contacts.block

- Added flags, my_stories_from parameters in contacts.unblock

- Added flags, my_stories_from parameters in contacts.getBlocked

- Added confirmed parameter in account.changeAuthorizationSettings

- Added from_side_menu, start_param parameters, changed type of url from string to flags.3?string in messages.requestSimpleWebView

- Added peer parameter in stories.canSendStory

- Added peer, media_areas parameters in stories.sendStory

- Added peer, media_areas parameters in stories.editStory

- Added peer parameter in stories.deleteStories

- Added peer parameter in stories.togglePinned

- Added peer parameter, removed user_id parameter in stories.getPinnedStories

- Added peer parameter in stories.getStoriesArchive

- Added peer parameter, removed user_id parameter in stories.getStoriesByID

- Added peer parameter, removed user_id parameter in stories.readStories

- Added peer parameter, removed user_id parameter in stories.incrementStoryViews

- Added flags, just_contacts, reactions_first, peer, q, offset parameters, removed offset_date, offset_id parameters in stories.getStoryViewsList

- Added peer parameter in stories.getStoriesViews

- Added peer parameter, removed user_id parameter in stories.exportStoryLink

- Added peer parameter, removed user_id parameter in stories.report

##### Deleted Methods

- Removed contacts.toggleStoriesHidden

- Removed stories.getUserStories

- Removed stories.getAllReadUserStories

- Removed users.getStoriesMaxIDs

##### New Constructors

- Added updateNewAuthorization - A new session logged into the current user's account through an unknown device.

- Added storiesStealthMode - Information about the current stealth mode session.

- Added updateStoriesStealthMode - Indicates that stories stealth mode was activated.

- Added mediaAreaCoordinates - Coordinates and size of a clicable rectangular area on top of a story.

- Added mediaAreaVenue - Represents a location tag attached to a story, with additional venue information.

- Added inputMediaAreaVenue - Represents a location tag attached to a story, with additional venue information.

- Added mediaAreaGeoPoint - Represents a geolocation tag attached to a story.

- Added updateSentStoryReaction - Indicates we reacted to a story ».

- Added mediaAreaSuggestedReaction - Represents a reaction bubble.

- Added peerStories - Stories associated to a peer

- Added stories.peerStories - Active story list of a specific peer.

- Added stories.boostsStatus - The current boost status » of a channel.

- Added stories.canApplyBoostOk - We're not boosting any channel, and we can freely boost the specified channel.

- Added stories.canApplyBoostReplace - We're boosting another channel, but we can freely boost the specified channel.

- Added booster - Info about a boost made by a specific user.

- Added stories.boostersList - Info about the users currently boosting the channel.

##### Changed Constructors

- Removed view_forum_as_messages parameter in dialog

- Added blocked_my_stories_from parameter, changed type of stories from flags.25?UserStories to flags.25?PeerStories in userFull

- Removed video, round, voice parameters in messageMediaDocument

- Added unconfirmed parameter in authorization

- Added flags, date parameters in updateReadMessagesContents

- Added stories_hidden, stories_hidden_min, stories_unavailable, stories_max_id parameters in channel

- Added stories_pinned_available, stories parameters in channelFull

- Added terms_url parameter, removed recurring_terms_url parameter in invoice

- Added from_request parameter in messageActionBotAllowed

- Added post_stories, edit_stories, delete_stories parameters in chatAdminRights

- Added flags, blocked_my_stories_from parameters, changed type of blocked from Bool to flags.0?true in updatePeerBlocked

- Added show_in_attach_menu, show_in_side_menu, side_menu_disclaimer_needed parameters, changed type of peer_types from Vector<AttachMenuPeerType> to flags.3?Vector<AttachMenuPeerType> in attachMenuBot

- Added has_settings parameter in messages.botApp

- Added has_viewers, forwards_count, reactions, reactions_count parameters in storyViews

- Added out, media_areas, sent_reaction parameters in storyItem

- Added peer parameter, removed user_id parameter in updateStory

- Added peer parameter, removed user_id parameter in updateReadStories

- Added flags, stealth_mode parameters in stories.allStoriesNotModified

- Added peer_stories, chats, stealth_mode parameters, removed user_stories parameter in stories.allStories

- Added chats parameter in stories.stories

- Added flags, blocked, blocked_my_stories_from, reaction parameters in storyView

- Added flags, reactions_count, next_offset parameters in stories.storyViewsList

- Added peer parameter, removed user_id parameter in inputMediaStory

- Added peer parameter, removed user_id parameter in messageMediaStory

- Added peer parameter, removed user_id parameter in webPageAttributeStory

##### Deleted Constructors

- Removed userStories

- Removed stories.userStories

#### PUSH notification changes

##### New PUSH notifications

- Added CHANNEL_MESSAGE_STORY - {1} shared a story

- Added CHAT_MESSAGE_STORY - {1} shared a story to the group

- Added MESSAGE_STORY - {1} shared a story with you

- Added MESSAGE_STORY_MENTION - {1} mentioned you in a story

- Added STORY_HIDDEN_AUTHOR - A new story was posted (comment: emitted when previews are hidden for this peer)

- Added STORY_NOTEXT - {1} posted a story

#### Schema

### Layer 160

#### Schema changes

##### New Methods

- Added contacts.editCloseFriends - Edit the close friends list, see here » for more info.

- Added contacts.toggleStoriesHidden

- Added stories.canSendStory - Check whether we can post stories as the specified peer.

- Added stories.sendStory - Uploads a Telegram Story.

- Added stories.editStory - Edit an uploaded story

- Added stories.deleteStories - Deletes some posted stories.

- Added stories.togglePinned - Pin or unpin one or more stories

- Added stories.getAllStories - Fetch the List of active (or active and hidden) stories, see here » for more info on watching stories.

- Added stories.getUserStories

- Added stories.getPinnedStories - Fetch the stories pinned on a peer's profile.

- Added stories.getStoriesArchive - Fetch the story archive » of a peer we control.

- Added stories.getStoriesByID - Obtain full info about a set of stories by their IDs.

- Added stories.toggleAllStoriesHidden - Hide the active stories of a specific peer, preventing them from being displayed on the action bar on the homescreen.

- Added stories.getAllReadUserStories

- Added stories.readStories - Mark all stories up to a certain ID as read, for a given peer; will emit an updateReadStories update to all logged-in sessions.

- Added stories.incrementStoryViews - Increment the view counter of one or more stories.

- Added stories.getStoryViewsList - Obtain the list of users that have viewed a specific story we posted

- Added stories.getStoriesViews - Obtain info about the view count, forward count, reactions and recent viewers of one or more stories.

- Added stories.exportStoryLink - Generate a story deep link for a specific story

- Added stories.report - Report a story.

- Added users.getStoriesMaxIDs

##### Changed Methods

- Added reply_to parameter, removed reply_to_msg_id, top_msg_id parameters in messages.sendMessage

- Added reply_to parameter, removed reply_to_msg_id, top_msg_id parameters in messages.sendMedia

- Added reply_to parameter, removed reply_to_msg_id, top_msg_id parameters in messages.sendInlineBotResult

- Added reply_to parameter, removed reply_to_msg_id parameter in messages.sendScreenshotNotification

- Added reply_to parameter, removed reply_to_msg_id, top_msg_id parameters in messages.sendMultiMedia

- Added compare_stories parameter in account.getNotifyExceptions

- Added reply_to parameter, removed reply_to_msg_id, top_msg_id parameters in messages.requestWebView

- Added reply_to parameter, removed reply_to_msg_id, top_msg_id parameters in messages.prolongWebView

##### New Constructors

- Added storyViews - Aggregated view and reaction information of a story.

- Added storyItemDeleted - Represents a previously active story, that was deleted

- Added storyItemSkipped - Represents an active story, whose full information was omitted for space and performance reasons; use stories.getStoriesByID to fetch full info about the skipped story when and if needed.

- Added storyItem - Represents a story.

- Added userStories

- Added updateStory - A new story was posted.

- Added updateReadStories - Stories of a specific peer were marked as read.

- Added stories.allStoriesNotModified - The list of active (or active and hidden) stories has not changed.

- Added stories.allStories - Full list of active (or active and hidden) stories.

- Added stories.stories - List of stories

- Added stories.userStories

- Added inputPrivacyValueAllowCloseFriends - Allow only close friends »

- Added privacyValueAllowCloseFriends - Allow only close friends »

- Added storyView - Story view date and reaction information

- Added stories.storyViewsList - Reaction and view counters for a story

- Added stories.storyViews - Reaction and view counters for a list of stories

- Added inputReplyToMessage - Reply to a message.

- Added inputReplyToStory - Reply to a story.

- Added messageReplyStoryHeader - Represents a reply to a story

- Added updateStoryID - A story was successfully uploaded.

- Added exportedStoryLink - Represents a story deep link.

- Added inputMediaStory - Forwarded story

- Added messageMediaStory - Represents a forwarded story or a story mention.

- Added webPageAttributeStory - Webpage preview of a Telegram story

##### Changed Constructors

- Added view_forum_as_messages parameter in dialog

- Added stories_muted, stories_hide_sender, stories_sound parameters in inputPeerNotifySettings

- Added stories_muted, stories_hide_sender, stories_ios_sound, stories_android_sound, stories_other_sound parameters in peerNotifySettings

- Added stories_pinned_available, stories parameters in userFull

- Added video, round, voice, alt_document parameters in messageMediaDocument

- Added nosound, preload_prefix_size parameters, changed type of duration from int to double in documentAttributeVideo

- Added close_friend, stories_hidden, stories_unavailable, stories_max_id parameters in user

- Added stories_preload parameter in autoDownloadSettings

- Added keep_archived_unmuted, keep_archived_folders parameters, changed type of archive_and_mute_new_noncontact_peers from flags.0?Bool to flags.0?true in globalPrivacySettings

##### Deleted Constructors

- Removed messageEntityBlockquote

#### Schema

### Layer 159

Introducing privacy settings for user bios, improved login code invalidation, improved chat invites, improved update handling, sponsored websites and click reporting for sponsored messages.

Also, anonymous channels can now vote in polls: when invoking messages.sendVote, the vote will be sent from the peer specified using messages.saveDefaultSendAs.

#### Schema changes

##### New Methods

- Added account.invalidateSignInCodes - Invalidate the specified login codes, see here » for more info.

- Added channels.clickSponsoredMessage - Informs the server that the user has either:

##### Changed Methods

- Added pts_limit, qts_limit parameters in updates.getDifference

##### New Constructors

- Added messagePeerVote - How a peer voted in a poll

- Added messagePeerVoteInputOption - How a peer voted in a poll (reduced constructor, returned if an option was provided to messages.getPollVotes)

- Added messagePeerVoteMultiple - How a peer voted in a multiple-choice poll

- Added inputPrivacyKeyAbout - Whether people can see your bio

- Added privacyKeyAbout - Whether people can see your bio

- Added sponsoredWebPage - Represents a sponsored website.

##### Changed Constructors

- Added verified, scam, fake parameters in chatInvite

- Changed type of recent_voters from flags.3?Vector<long> to flags.3?Vector<Peer> in pollResults

- Added small_queue_active_operations_max, large_queue_active_operations_max parameters in autoDownloadSettings

- Added peer parameter, removed user_id parameter in updateMessagePollVote

- Added chats parameter, changed type of votes from Vector<MessageUserVote> to Vector<MessagePeerVote> in messages.votesList

- Added webpage parameter in sponsoredMessage

##### Deleted Constructors

- Removed messageUserVote

- Removed messageUserVoteInputOption

- Removed messageUserVoteMultiple

#### Schema

### Layer 158

To view all the changes since the last update, start reading the changelog @ Layer 146.

Most importantly, layer 152 added support for Firebase SMS authentication, which in some conditions may be required by the server in order to send SMS codes.
Currently, only official apps can make use of Firebase SMS authentication: this means that in some conditions, only the official applications can receive a login/signup code via SMS/call.
Third-party apps may log in using any of the other code delivery methods (Telegram codes, Fragment codes, email codes, future auth tokens, QR codes).

And now, here are the changes made in this layer:

You can now share folders », use collectible usernames for bots », set custom per-chat wallpapers » and reset the login email ».
Users may now edit the usernames, name, about text, description and profile picture of bots they own using the API.
Bots can now directly invoke photos.updateProfilePhoto and photos.uploadProfilePhoto to edit their own profile picture.
Bots may also now specify a custom peer filter when using keyboardButtonSwitchInline buttons.

Added the small_queue_max_active_operations_count » and large_queue_max_active_operations_count » client configuration parameters, used to limit parallelism when downloading multiple files in parallel from the same DC as described in the docs ».

The RPC error database » was also updated, and a small clarification for open-source push notification standards like UnifiedPush was added to the push notifications documentation ».

#### Schema changes

##### New Methods

- Added auth.resetLoginEmail - Reset the login email ».

- Added chatlists.exportChatlistInvite - Export a folder », creating a chat folder deep link ».

- Added chatlists.deleteExportedInvite - Delete a previously created chat folder deep link ».

- Added chatlists.editExportedInvite - Edit a chat folder deep link ».

- Added chatlists.getExportedInvites - List all chat folder deep links » associated to a folder

- Added chatlists.checkChatlistInvite - Obtain information about a chat folder deep link ».

- Added chatlists.joinChatlistInvite - Import a chat folder deep link », joining some or all the chats in the folder.

- Added chatlists.getChatlistUpdates - Fetch new chats associated with an imported chat folder deep link ». Must be invoked at most every chatlist_update_period seconds (as per the related client configuration parameter »).

- Added chatlists.joinChatlistUpdates - Join channels and supergroups recently added to a chat folder deep link ».

- Added chatlists.hideChatlistUpdates - Dismiss new pending peers recently added to a chat folder deep link ».

- Added chatlists.getLeaveChatlistSuggestions - Returns identifiers of pinned or always included chats from a chat folder imported using a chat folder deep link », which are suggested to be left when the chat folder is deleted.

- Added chatlists.leaveChatlist - Delete a folder imported using a chat folder deep link »

- Added bots.reorderUsernames - Reorder usernames associated to a bot we own.

- Added bots.toggleUsername - Activate or deactivate a purchased fragment.com username associated to a bot we own.

- Added messages.setChatWallPaper - Set a custom wallpaper » in a specific private chat with another user.

##### Changed Methods

- Added bot parameter in photos.updateProfilePhoto

- Added bot parameter in photos.uploadProfilePhoto

- Added flags, for_chat parameters in account.uploadWallPaper

- Added bot, name parameters in bots.setBotInfo

- Changed type of bots.getBotInfo from Vector<string> to bots.BotInfo

- Added flags, bot parameters in bots.getBotInfo

##### Deleted Methods

- Removed messages.getAllChats

- Removed folders.deleteFolder

##### New Constructors

- Added dialogFilterChatlist - A folder imported using a chat folder deep link ».

- Added inputChatlistDialogFilter - Folder ID

- Added exportedChatlistInvite - Exported chat folder deep link ».

- Added chatlists.exportedChatlistInvite - Info about an exported chat folder deep link ».

- Added chatlists.exportedInvites - Info about multiple chat folder deep links ».

- Added chatlists.chatlistInviteAlready - Updated info about a chat folder deep link » we already imported.

- Added chatlists.chatlistInvite - Info about a chat folder deep link ».

- Added chatlists.chatlistUpdates - Updated information about a chat folder deep link ».

- Added messageActionSetChatWallPaper - The wallpaper » of the current chat was changed.

- Added messageActionSetSameChatWallPaper - The user applied a wallpaper » previously sent by the other user in a messageActionSetChatWallPaper message.

- Added bots.botInfo - Localized information about a bot.

- Added inlineQueryPeerTypeBotPM - Peer type: private chat with a bot.

##### Changed Constructors

- Added wallpaper parameter in userFull

- Added bot_can_edit parameter in user

- Added peer_types parameter in keyboardButtonSwitchInline

- Added via_chatlist parameter in updateChannelParticipant

- Added via_chatlist parameter in chatInviteImporter

- Added flags, via_chatlist parameters in channelAdminLogEventActionParticipantJoinByInvite

- Added my parameter in messagePeerReaction

- Added flags, crypto_currency, crypto_amount parameters in messageActionGiftPremium

- Added reset_available_period, reset_pending_date parameters, removed next_phone_login_date parameter in auth.sentCodeTypeEmailCode

#### Schema

### Layer 155

Reaction dates.

#### Schema changes

##### Changed Constructors

- Added date parameter in messagePeerReaction

#### Schema

### Layer 154

Added support for named Mini Apps, which can be opened from a Direct Mini App link.
Web apps can now be opened by clicking on a switch_webview inline result, similar to switch_pm inline results.
Bots can now edit and localize their own about text and description.
The current future auth token is now directly returned in the config constructor, which was also cleaned up to remove redundant information already contained in the appConfig configuration.
messages.getMessageReadParticipants now returns a timestamp for each user, indicating when that user has read the specified message.

When using messages.addChatUser, channels.inviteToChannel or messages.createChat, 0-N updates of type updateGroupInvitePrivacyForbidden may now be returned, indicating that the server couldn't add a user to a chat because of their privacy settings; if required, an invite link can be shared with the user, instead.

Sponsored messages can now contain detailed info about the sponsor of the message or the message itself.

#### Schema changes

##### New Methods

- Added messages.getBotApp - Obtain information about a direct link Mini App

- Added messages.requestAppWebView - Open a bot mini app from a direct Mini App deep link, sending over user information after user confirmation.

- Added bots.setBotInfo - Set localized name, about text and description of a bot (or of the current account, if called by a bot).

- Added bots.getBotInfo - Get localized name, about text and description of a bot (or of the current account, if called by a bot).

##### Changed Methods

- Added switch_webview parameter in messages.setInlineBotResults

- Changed type of messages.getMessageReadParticipants from Vector<long> to Vector<ReadParticipantDate>

- Added from_switch_webview parameter in messages.requestSimpleWebView

##### New Constructors

- Added inputBotAppID - Used to fetch information about a direct link Mini App by its ID

- Added inputBotAppShortName - Used to fetch information about a direct link Mini App by its short name

- Added botAppNotModified - Bot app info hasn't changed.

- Added botApp - Contains information about a direct link Mini App.

- Added messages.botApp - Contains information about a direct link Mini App

- Added appWebViewResultUrl - Contains the link that must be used to open a direct link Mini App.

- Added inlineBotWebView - Specifies an inline mode mini app button, shown on top of the inline query results list.

- Added readParticipantDate - Contains info about when a certain participant has read a message

- Added updateGroupInvitePrivacyForbidden - 0-N updates of this type may be returned only when invoking messages.addChatUser, channels.inviteToChannel or messages.createChat: it indicates we couldn't add a user to a chat because of their privacy settings; if required, an invite link can be shared with the user, instead.

##### Changed Constructors

- Added autologin_token parameter, removed phonecalls_enabled, ignore_phone_entities, pfs_enabled, saved_gifs_limit, stickers_faved_limit, pinned_dialogs_count_max, pinned_infolder_count_max parameters in config

- Added switch_webview parameter in messages.botResults

- Added flags, attach_menu, app parameters, changed type of domain from string to flags.0?string in messageActionBotAllowed

- Added sponsor_info, additional_info parameters in sponsoredMessage

#### Schema

### Layer 153

Allow bots to modify stickersets they created, allow changing the thumbnail of custom emoji stickersets and improve client configuration caching.

#### Schema changes

##### New Methods

- Added stickers.changeSticker - Update the keywords, emojis or mask coordinates of a sticker, bots only.

- Added stickers.renameStickerSet - Renames a stickerset, bots only.

- Added stickers.deleteStickerSet - Deletes a stickerset we created, bots only.

##### Changed Methods

- Changed type of help.getAppConfig from JSONValue to help.AppConfig

- Added hash parameter in help.getAppConfig

- Added flags, thumb_document_id parameters, changed type of thumb from InputDocument to flags.0?InputDocument in stickers.setStickerSetThumb

##### New Constructors

- Added help.appConfigNotModified - The client configuration parameters haven't changed

- Added help.appConfig - Contains various client configuration parameters

##### Changed Constructors

- Added keywords parameter in inputStickerSetItem

#### Schema

### Layer 152

Users can now set stickers or custom emojis as profile or group/channel pictures », and Telegram Premium users can enable real-time chat translation », which allows seamless translation of chat messages, keeping style entities intact.
Bots can now prompt the user to select and share a peer with the bot with messages.sendBotRequestedPeer, by using a keyboardButtonRequestPeer bot button.
Added support for categorized custom emojis », a messages.searchCustomEmoji method to look up custom emojis by their corresponding UTF8 emoji and added custom emoji stickerset deep links.
Also implemented synchronization of media autosave settings.

Future auth token login now works even for accounts without 2FA.

Most importantly, added support for Firebase SMS authentication, which in some conditions may be required by the server in order to send SMS codes.
Currently, only official apps can make use of Firebase SMS authentication: this means that in some conditions, only the official applications can receive a login/signup code via SMS/call.
Third-party apps may log in using any of the other code delivery methods (Telegram codes, Fragment codes, email codes, future auth tokens, QR codes).

#### Schema changes

##### New Methods

- Added messages.sendBotRequestedPeer - Send one or more chosen peers, as requested by a keyboardButtonRequestPeer button.

- Added account.getDefaultProfilePhotoEmojis - Get a set of suggested custom emoji stickers that can be used as profile picture

- Added account.getDefaultGroupPhotoEmojis - Get a set of suggested custom emoji stickers that can be used as group picture

- Added auth.requestFirebaseSms - Request an SMS code via Firebase.

- Added messages.getEmojiGroups - Represents a list of emoji categories, to be used when selecting custom emojis.

- Added messages.getEmojiStatusGroups - Represents a list of emoji categories, to be used when selecting custom emojis to set as custom emoji status.

- Added messages.getEmojiProfilePhotoGroups - Represents a list of emoji categories, to be used when selecting custom emojis to set as profile picture.

- Added messages.searchCustomEmoji - Look for custom emojis associated to a UTF8 emoji

- Added messages.togglePeerTranslations - Show or hide the real-time chat translation popup for a certain chat

- Added account.getAutoSaveSettings - Get autosave settings

- Added account.saveAutoSaveSettings - Modify autosave settings

- Added account.deleteAutoSaveExceptions - Clear all peer-specific autosave settings.

##### Changed Methods

- Added video_emoji_markup parameter in photos.uploadProfilePhoto

- Added id parameter, removed msg_id, from_lang parameters, changed type of text from flags.1?string to flags.1?Vector<TextWithEntities> in messages.translateText

- Added video_emoji_markup parameter in photos.uploadContactProfilePhoto

##### New Constructors

- Added auth.sentCodeSuccess - The user successfully authorized using future auth tokens

- Added messageActionRequestedPeer - Contains info about one or more peers that the user shared with the bot after clicking on a keyboardButtonRequestPeer button.

- Added requestPeerTypeUser - Choose a user.

- Added requestPeerTypeChat - Choose a chat or supergroup

- Added requestPeerTypeBroadcast - Choose a channel

- Added keyboardButtonRequestPeer - Prompts the user to select and share one or more peers with the bot using messages.sendBotRequestedPeer

- Added emojiListNotModified - The list of custom emojis hasn't changed.

- Added emojiList - Represents a list of custom emojis.

- Added auth.sentCodeTypeFirebaseSms - An authentication code should be delivered via SMS after Firebase attestation, as described in the auth documentation ».

- Added emojiGroup - Represents an emoji category.

- Added messages.emojiGroupsNotModified - The list of emoji categories hasn't changed.

- Added messages.emojiGroups - Represents a list of emoji categories.

- Added videoSizeEmojiMarkup - An animated profile picture based on a custom emoji sticker.

- Added videoSizeStickerMarkup - An animated profile picture based on a sticker.

- Added textWithEntities - Styled text with message entities

- Added messages.translateResult - Translated text with entities

- Added autoSaveSettings - Media autosave settings

- Added autoSaveException - Peer-specific media autosave settings

- Added account.autoSaveSettings - Contains media autosave settings

- Added updateAutoSaveSettings - Media autosave settings have changed and must be refetched using account.getAutoSaveSettings.

##### Changed Constructors

- Added video_emoji_markup parameter in inputChatUploadedPhoto

- Added translations_disabled parameter in chatFull

- Added future_auth_token parameter in auth.authorization

- Added translations_disabled parameter in userFull

- Added translations_disabled parameter in channelFull

- Added send_photos, send_videos, send_roundvideos, send_audios, send_voices, send_docs, send_plain parameters in chatBannedRights

- Added allow_firebase, token, app_sandbox parameters in codeSettings

- Added transaction parameter in premiumSubscriptionOption

##### Deleted Constructors

- Removed messages.translateNoResult

- Removed messages.translateResultText

#### Schema

### Layer 151

Introducing spoiler media, custom contact profile pictures, hidden supergroup participants and persistent bot keyboards.
Attachment menu bot mini apps may now ask permission to write direct messages to the users that install them.

#### Schema changes

##### New Methods

- Added photos.uploadContactProfilePhoto - Upload a custom profile picture for a contact, or suggest a new profile picture to a contact.

- Added channels.toggleParticipantsHidden - Hide or display the participants list in a supergroup.

##### Changed Methods

- Added flags, fallback parameters in photos.updateProfilePhoto

- Added fallback parameter in photos.uploadProfilePhoto

- Added flags, write_allowed parameters in messages.toggleBotInAttachMenu

##### New Constructors

- Added messageActionSuggestProfilePhoto - A new profile picture was suggested using photos.uploadContactProfilePhoto.

- Added stickerSetNoCovered - Just the stickerset information, with no previews.

- Added updateUser - User information was updated, it must be refetched using users.getFullUser.

##### Changed Constructors

- Added spoiler parameter in inputMediaUploadedPhoto

- Added spoiler parameter in inputMediaPhoto

- Added personal parameter in userProfilePhoto

- Added spoiler parameter in messageMediaPhoto

- Added personal_photo, fallback_photo parameters in userFull

- Added spoiler parameter in inputMediaUploadedDocument

- Added spoiler parameter in inputMediaDocument

- Added spoiler parameter in messageMediaDocument

- Added persistent parameter in replyKeyboardMarkup

- Added participants_hidden parameter in channelFull

- Added spoiler parameter in inputMediaPhotoExternal

- Added spoiler parameter in inputMediaDocumentExternal

- Added request_write_access parameter in attachMenuBot

##### Deleted Constructors

- Removed updateUserPhoto

#### Schema

### Layer 150

Fragment » phone numbers, temporary profile links », native group antispam », message autodeletion in groups, allow hiding the "General" forum topic.

Also added a new autodelete settings deep link » and a profile settings deep link ».

#### Schema changes

##### New Methods

- Added channels.toggleAntiSpam - Enable or disable the native antispam system.

- Added channels.reportAntiSpamFalsePositive - Report a native antispam false positive

- Added messages.setDefaultHistoryTTL - Changes the default value of the Time-To-Live setting, applied to all new chats.

- Added messages.getDefaultHistoryTTL - Gets the default value of the Time-To-Live setting, applied to all new chats.

- Added contacts.exportContactToken - Generates a temporary profile link for the currently logged-in user.

- Added contacts.importContactToken - Obtain user info from a temporary profile link.

##### Changed Methods

- Added flags, ttl_period parameters in messages.createChat

- Added forum, ttl_period parameters in channels.createChannel

- Added hidden parameter in channels.editForumTopic

##### New Constructors

- Added defaultHistoryTTL - Contains info about the default value of the Time-To-Live setting, applied to all new chats.

- Added auth.codeTypeFragmentSms - The next time, the authentication code will be delivered via fragment.com

- Added auth.sentCodeTypeFragmentSms - The code was delivered via fragment.com.

- Added exportedContactToken - Describes a temporary profile link.

- Added channelAdminLogEventActionToggleAntiSpam - Native antispam functionality was enabled or disabled.

##### Changed Constructors

- Added ttl_period parameter in dialog

- Added antispam parameter in channelFull

- Added flags, auto_setting_from parameters in messageActionSetMessagesTTL

- Added hidden parameter in messageActionTopicEdit

#### Schema

### Layer 149

Pinned forum topics.

#### Schema changes

##### New Methods

- Added channels.reorderPinnedForumTopics - Reorder pinned forum topics

##### New Constructors

- Added updateChannelPinnedTopics - The pinned topics of a forum have changed.

##### Changed Constructors

- Added topics parameter in messages.channelMessages

- Added pinned parameter, changed type of topic_id from flags.0?int to int in updateChannelPinnedTopic

#### Schema

### Layer 148

Collectible usernames », groups with topics (aka forums »), sponsored message improvements.
Added support for thread IDs in message deep links », which now double as forum topic deep links », and added a new manage_topics parameter to group/channel bot deep links.

#### Schema changes

##### New Methods

- Added account.reorderUsernames - Reorder usernames associated with the currently logged-in user.

- Added account.toggleUsername - Activate or deactivate a purchased fragment.com username associated to the currently logged-in user.

- Added channels.reorderUsernames - Reorder active usernames

- Added channels.toggleUsername - Activate or deactivate a purchased fragment.com username associated to a supergroup or channel we own.

- Added channels.deactivateAllUsernames - Disable all purchased usernames of a supergroup or channel

- Added channels.toggleForum - Enable or disable forum functionality in a supergroup.

- Added channels.createForumTopic - Create a forum topic; requires manage_topics rights.

- Added channels.getForumTopics - Get topics of a forum

- Added channels.getForumTopicsByID - Get forum topics by their ID

- Added channels.editForumTopic - Edit forum topic; requires manage_topics rights.

- Added channels.updatePinnedForumTopic - Pin or unpin forum topics

- Added channels.deleteTopicHistory - Delete message history of a forum topic

##### Changed Methods

- Added top_msg_id parameter in messages.sendMessage

- Added top_msg_id parameter in messages.sendMedia

- Added top_msg_id parameter in messages.forwardMessages

- Added top_msg_id parameter in messages.sendInlineBotResult

- Added top_msg_id parameter in messages.saveDraft

- Added flags, top_msg_id parameters in messages.getUnreadMentions

- Added flags, top_msg_id parameters in messages.readMentions

- Added top_msg_id parameter in messages.sendMultiMedia

- Added flags, top_msg_id parameters in messages.getSearchCounters

- Removed document_id parameter in account.getTheme

- Added flags, top_msg_id parameters in messages.unpinAllMessages

- Added flags, top_msg_id parameters in messages.getUnreadReactions

- Added flags, top_msg_id parameters in messages.readReactions

- Added top_msg_id parameter in messages.requestWebView

- Added top_msg_id parameter in messages.prolongWebView

##### New Constructors

- Added username - Contains information about a username.

- Added channelAdminLogEventActionChangeUsernames - The list of usernames associated with the channel was changed

- Added channelAdminLogEventActionToggleForum - Forum functionality was enabled or disabled.

- Added channelAdminLogEventActionCreateTopic - A forum topic was created

- Added channelAdminLogEventActionEditTopic - A forum topic was edited

- Added channelAdminLogEventActionDeleteTopic - A forum topic was deleted

- Added channelAdminLogEventActionPinTopic - A forum topic was pinned or unpinned

- Added forumTopicDeleted - Represents a deleted forum topic.

- Added forumTopic - Represents a forum topic.

- Added messages.forumTopics - Contains information about multiple forum topics

- Added messageActionTopicCreate - A forum topic was created.

- Added messageActionTopicEdit - Forum topic information was edited.

- Added updateChannelPinnedTopic - A forum topic » was pinned or unpinned.

- Added inputNotifyForumTopic - Notifications generated by a topic in a forum.

- Added notifyForumTopic - Notifications generated by a topic in a forum.

- Added inputStickerSetEmojiDefaultTopicIcons - Default custom emoji stickerset for forum topic icons

- Added messages.sponsoredMessagesEmpty - No sponsored messages are available.

##### Changed Constructors

- Added usernames parameter, removed username parameter in updateUserName

- Added flags2, usernames parameters in user

- Added forum, flags2, usernames parameters in channel

- Added flags, top_msg_id parameters in updateDraftMessage

- Added forums parameter in channelAdminLogEventsFilter

- Added flags, top_msg_id parameters in updateChannelReadMessagesContents

- Added manage_topics parameter in chatAdminRights

- Added manage_topics parameter in chatBannedRights

- Added forum_topic parameter in messageReplyHeader

- Added show_peer_photo parameter in sponsoredMessage

- Added flags, posts_between parameters in messages.sponsoredMessages

- Added flags, top_msg_id parameters in updateMessageReactions

#### Schema

### Layer 147

Keywords for custom emojis and non-mask stickers, web token authorization.

#### Schema changes

##### New Methods

- Added auth.importWebTokenAuthorization - Login by importing an authorization token

##### New Constructors

- Added stickerKeyword - Keywords for a certain sticker

##### Changed Constructors

- Added keywords parameter in messages.stickerSet

- Added keywords parameter in stickerSetFullCovered

#### Schema

### Layer 146

Scheduled replies to scheduled messages, accent colors for custom emojis.

#### Schema changes

##### New Methods

- Added messages.getExtendedMedia - Get information about extended media

##### Changed Methods

- Added emojis, text_color parameters in stickers.createStickerSet

##### New Constructors

- Added messageExtendedMediaPreview - Extended media preview

- Added messageExtendedMedia - Extended media

- Added updateMessageExtendedMedia - Extended media update

##### Changed Constructors

- Added extended_media parameter in inputMediaInvoice

- Added extended_media parameter in messageMediaInvoice

- Added reply_to_scheduled parameter in messageReplyHeader

- Added text_color parameter in documentAttributeCustomEmoji

- Added upgrade parameter in inputStorePaymentPremiumSubscription

- Added current, can_purchase_upgrade parameters in premiumSubscriptionOption

#### Schema

### Layer 145

Custom emoji statuses, custom emoji & multiple message reactions, login via email, recent stickersets, Telegram Premium and bot mini app improvements.

Added the following brand new documentation articles:

- Deep links

- Stickers

- Themes

- Wallpapers

Also added more details on entity length calculation and AUTH_KEY_DUPLICATED errors.

The RPC error database » was also updated.

#### Schema changes

##### New Methods

- Added account.updateEmojiStatus - Set an emoji status

- Added account.getDefaultEmojiStatuses - Get a list of default suggested emoji statuses

- Added account.getRecentEmojiStatuses - Get recently used emoji statuses

- Added account.clearRecentEmojiStatuses - Clears list of recently used emoji statuses

- Added messages.reportReaction - Report a message reaction

- Added messages.getTopReactions - Got popular message reactions

- Added messages.getRecentReactions - Get recently used message reactions

- Added messages.clearRecentReactions - Clear recently used message reactions

##### Changed Methods

- Added flags, email_verification parameters, changed type of phone_code from string to flags.0?string in auth.signIn

- Added update_stickersets_order parameter in messages.sendMessage

- Added update_stickersets_order parameter in messages.sendMedia

- Added update_stickersets_order parameter in messages.sendMultiMedia

- Added purpose parameter in account.sendVerifyEmailCode

- Changed type of account.verifyEmail from Bool to account.EmailVerified

- Added purpose, verification parameters, removed email, code parameters in account.verifyEmail

- Added add_to_recent parameter, changed type of reaction from flags.0?string to flags.0?Vector<Reaction> in messages.sendReaction

- Changed type of reaction from flags.0?string to flags.0?Reaction in messages.getMessageReactionsList

- Changed type of available_reactions from Vector<string> to ChatReactions in messages.setChatAvailableReactions

- Changed type of reaction from string to Reaction in messages.setDefaultReaction

- Added platform parameter in messages.requestWebView

- Added platform parameter in messages.requestSimpleWebView

##### New Constructors

- Added emojiStatusEmpty - No emoji status is set

- Added emojiStatus - An emoji status

- Added emojiStatusUntil - An emoji status valid until the specified date

- Added updateUserEmojiStatus - The emoji status of a certain user has changed

- Added updateRecentEmojiStatuses - The list of recent emoji statuses has changed

- Added account.emojiStatusesNotModified - The server-side list of emoji statuses hasn't changed

- Added account.emojiStatuses - A list of emoji statuses

- Added reactionEmpty - No reaction

- Added reactionEmoji - Normal emoji message reaction

- Added reactionCustomEmoji - Custom emoji message reaction

- Added chatReactionsNone - No reactions are allowed

- Added chatReactionsAll - All reactions or all non-custom reactions are allowed

- Added chatReactionsSome - Some reactions are allowed

- Added messages.reactionsNotModified - The server-side list of message reactions hasn't changed

- Added messages.reactions - List of message reactions

- Added updateRecentReactions - The list of recent message reactions has changed

- Added updateMoveStickerSetToTop - A stickerset was just moved to top, see here for more info »

- Added auth.sentCodeTypeEmailCode - The code was sent via the previously configured login email »

- Added auth.sentCodeTypeSetUpEmailRequired - The user should add and verify an email address in order to login as described here ».

- Added emailVerifyPurposeLoginSetup - Email verification purpose: setup login email

- Added emailVerifyPurposeLoginChange - Email verification purpose: change login email

- Added emailVerifyPurposePassport - Verify an email for use in telegram passport

- Added emailVerificationCode - Email verification code

- Added emailVerificationGoogle - Google ID email verification token

- Added emailVerificationApple - Apple ID email verification token

- Added account.emailVerified - The email was verified correctly.

- Added account.emailVerifiedLogin - The email was verified correctly, and a login code was just sent to it.

- Added premiumSubscriptionOption - Describes a Telegram Premium subscription option

- Added inputStickerSetEmojiGenericAnimations - Generic animation stickerset containing animations to play when reacting to messages using a normal emoji without a custom animation

- Added inputStickerSetEmojiDefaultStatuses - Default custom emoji status stickerset

- Added sendAsPeer - Indicates a peer that can be used to send messages

##### Changed Constructors

- Changed type of available_reactions from flags.18?Vector<string> to flags.18?ChatReactions in chatFull

- Added reactions_default parameter in config

- Added login_email_pattern parameter in account.password

- Added emoji_status parameter in user

- Changed type of available_reactions from flags.30?Vector<string> to flags.30?ChatReactions in channelFull

- Added flags, masks, emojis parameters in updateStickerSets

- Changed type of peers from Vector<Peer> to Vector<SendAsPeer> in channels.sendAsPeers

- Added chosen_order parameter, removed chosen parameter, changed type of reaction from string to Reaction in reactionCount

- Changed type of prev_value from Vector<string> to ChatReactions, new_value from Vector<string> to ChatReactions in channelAdminLogEventActionChangeAvailableReactions

- Changed type of reaction from string to Reaction in messagePeerReaction

- Added period_options parameter, removed currency, monthly_amount parameters in help.premiumPromo

#### Schema

### Layer 144

Users can now send custom emojis, gift Telegram Premium to other users, and download album covers for any music file.
Also introducing new voice message privacy settings and support for additional payment methods.

The E2E schema was updated to account for previous changes in the main schema (custom emojis+spoiler entities).

#### Schema changes

##### New Methods

- Added messages.getCustomEmojiDocuments - Fetch custom emoji stickers ».

- Added messages.getEmojiStickers - Gets the list of currently installed custom emoji stickersets.

- Added messages.getFeaturedEmojiStickers - Gets featured custom emoji stickersets.

##### Changed Methods

- Added emojis parameter in messages.reorderStickerSets

- Added emojis parameter in messages.getArchivedStickers

- Added purpose parameter, removed flags, restore parameters in payments.assignAppStoreTransaction

- Added receipt, purpose parameters, removed purchase_token parameter in payments.assignPlayMarketTransaction

- Added purpose parameter in payments.canPurchasePremium

##### New Constructors

- Added messageEntityCustomEmoji - Represents a custom emoji.

- Added documentAttributeCustomEmoji - Info about a custom emoji

- Added stickerSetFullCovered - Stickerset preview with all stickers of the stickerset included.

- Added inputStorePaymentPremiumSubscription - Info about a Telegram Premium purchase

- Added inputStorePaymentGiftPremium - Info about a gifted Telegram Premium purchase

- Added messageActionGiftPremium - Info about a gifted Telegram Premium subscription

- Added premiumGiftOption - Telegram Premium gift option

- Added inputStickerSetPremiumGifts - Stickers to show when receiving a gifted Telegram Premium subscription

- Added updateReadFeaturedEmojiStickers - Some featured custom emoji stickers were marked as read

- Added inputPrivacyKeyVoiceMessages - Whether people can send you voice messages

- Added privacyKeyVoiceMessages - Whether the user accepts voice messages

- Added paymentFormMethod - Represents an additional payment method

- Added inputWebFileAudioAlbumThumbLocation - Used to download an album cover for any music file using upload.getWebFile, see the webfile docs for more info ».

##### Changed Constructors

- Added voice_messages_forbidden, premium_gifts parameters in userFull

- Added emojis, thumb_document_id parameters in stickerSet

- Added emojis parameter in updateStickerSetsOrder

- Added additional_methods parameter, changed type of saved_credentials from flags.1?PaymentSavedCredentials to flags.1?Vector<PaymentSavedCredentials> in payments.paymentForm

#### Schema

#### End-to-end schema changes

##### New Constructors

- Added messageEntitySpoiler - Message entity representing a spoiler

- Added messageEntityCustomEmoji - Represents a custom emoji.

#### End-to-end schema

### Layer 143

Telegram Premium, voice message transcription, invoices, bot description photos/animations, immediate account deletion, recurring payments and attachment menu improvements.
Also, discussion group admins can now require users to join before commenting.

The main and E2E schemes were also modified to eventually support uploading and downloading files bigger than 4GB: the current supported maximum filesize is dynamically specified, and can be fetched from the new upload_max_fileparts_default » and upload_max_fileparts_premium » app configuration fields.

