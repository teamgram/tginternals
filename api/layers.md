# Layers

Below you will find information on schema changes. For more details on the use of layers, see Invoking API methods.

### Layer 214

To view all changes since the last documentation refresh, start reading at layer 196.

This documentation refresh also brings the following changes:

- A brand new new file reference database map file »: can be used to automatically codegen a fully functional file reference database, see here » for more info.

- The map file generator is open source, and is specifically designed to be easy to run on newer, even experimental layers, see here for more info ».

- Layer diffs will now list changes to the file reference map file as well.

- The RPC error database was updated », and it now has the following extra fields:

- business_supported - Contains the full list of methods that can be used by bots over a business connection with invokeWithBusinessConnection.

- unauthed_allowed - Contains the full list of methods that can be used by not yet logged in connections.

- All methods in the documentation now explicitly state if they can be used by bots, users or both, and if they can be used over a business connection or over an unauthorized connection.

- Updated the list of methods that can be used over a business connection

- stories.sendStory and stories.editStory can also be used to post and edit stories on behalf of a connected business account: in this case, simply pass the business account's peer in peer, without wrapping the request in an invokeWithBusinessConnection » query.

- Note that stories.editStory can only be used to edit stories posted by the same business bot on behalf of the user.

- Updated the list of methods that can be used over an unauthed connection

- The documentation for the profile page was also reorganized, to include the full list of profile tabs to show, along with instructions on how to populate them ».

- Corrected hash generation instructions for messages.getScheduledHistory, the correct order is id, edit_date, date; not id, date, edit_date »

- Added documentation on frozen accounts »

- Added a new client configuration key for the maximum number of allowed quiz poll answers

- Added a new client configuration key for the maximum amount of Telegram Stars that can be withdrawn from a channel or bot's balance »

- Added support for age verification, if required by the current country's legislation ».

- Added device storage and secure storage APIs for mini apps, using the following events:

- web_app_device_storage_save_key - Save or remove a value from the device's local storage associated with this user and mini app

- web_app_device_storage_get_key - Get a value from the device's local storage associated with this user and mini app

- web_app_device_storage_clear - Clear the device's local storage associated with this user and mini app

- web_app_secure_storage_save_key - Save or remove a value from the device's secure storage associated with this user and mini app

- web_app_secure_storage_get_key - Get a value from the device's secure storage associated with this user and mini app

- web_app_secure_storage_restore_key - Restore a value to the device's secure storage associated with this user and mini app

- web_app_secure_storage_clear - Clear the device's secure storage associated with this user and mini app

- Add support for the new manage_direct_messages admin right in group/channel bot links.

- Updated the documentation for bot API dialog IDs to include support for the new monoforum ID range, see here » for more info.

- Specifically, the bot API dialog ID new ranges from -4000000000000 to 1099511627775 (previously the range was -2002147483648 to 1099511627775).

- The transformed range for bot API monoforum dialog IDs is -2002147483649 to -4000000000000 inclusively.

- Push notifications can now have a custom report_delivery_until_date parameter for Telegram Gateway verification messages: if set, the message is a telegram gateway verification code, and messages.reportMessagesDelivery should be invoked with the push flag set.

- Added a correction to the paid reactions documentation »: the random_id argument of messages.sendPaidReaction must be composed of a 64-bit integer where the lower 32 bits are random, and the higher 32 bits are equal to the current unixtime, i.e. uint64_t random_id = (time() << 32) | ((uint64_t)random_uint32_t()): this differs from the random_id format of all other methods in the API, which just take 64 random bits.

- Clarified that adding a new recent reaction should trigger modification of the cached list and regeneration of the hash with a custom algorithm, see here » for more info.

- Clarified that modifying saved message tags should trigger modification of the cached list and regeneration of the hash with a custom algorithm, see here » for more info.

- The webpage type list » was updated.

- Clarified that in some cases such as updates from big channels, the API may return constructors from older layers, different from the connection's current layer.

- Clients should treat this as a 500 server error, and handle it by closing and reopening the TCP socket, re-reinitializing the session with initConnection and invoking getDifference.

- A whole bunch of new features and articles, start reading at layer 196 to view them all.

And here are the changes in this layer:

- Set a collectible gift as chat theme »

- Allow sending an email to telegram's support team when getting auth.sentCodePaymentRequired during login (official clients only).

#### Schema changes

##### New Methods

- Added account.getUniqueGiftChatThemes - Obtain all chat themes » associated to owned collectible gifts ».

##### Changed Methods

- Added theme parameter, removed emoticon parameter in messages.setChatTheme

##### New Constructors

- Added chatTheme - A chat theme

- Added chatThemeUniqueGift - A chat theme based on a collectible gift ».

- Added account.chatThemesNotModified - The available chat themes were not modified

- Added account.chatThemes - Available chat themes

- Added inputChatThemeEmpty - Remove any currently configured theme.

- Added inputChatTheme - Set an emoji-based chat theme, returned by account.getChatThemes.

- Added inputChatThemeUniqueGift - Set a theme based on an owned collectible gift », returned by account.getUniqueGiftChatThemes.

##### Changed Constructors

- Added theme parameter, removed emoticon parameter in messageActionSetChatTheme

- Added support_email_address, support_email_subject parameters in auth.sentCodePaymentRequired

- Added theme parameter, removed theme_emoticon parameter in userFull

- Added theme_available, theme_peer parameters in starGiftUnique

#### Schema

#### File reference map file schema » changes

##### New Constructors

- Added boolFalse - Constructor may be interpreted as a booleanfalse value.

- Added boolTrue - The constructor can be interpreted as a booleantrue value.

- Added true - See predefined identifiers.

- Added vector - A universal vector constructor.

- Added fileReferenceOrigins

- Added locationIncoming

- Added locationOutgoing

- Added origin

- Added skippedOrigin

- Added action

- Added paramNotFlag

- Added paramIsFlagAbortIfEmpty

- Added paramIsFlagFallback

- Added paramIsFlagPassthrough

- Added pathPart

- Added path

- Added pathParent

- Added extractAndStore

- Added extractInputStickerSetFromDocumentAttributesAndStore

- Added extractInputStickerSetFromStickerSetAndStore

- Added extractPeerIdFromPeerAndStore

- Added extractPeerIdFromInputPeerAndStore

- Added extractChannelIdFromChannelAndStore

- Added extractChannelIdFromInputChannelAndStore

- Added extractUserIdFromUserAndStore

- Added extractUserIdFromInputUserAndStore

- Added callOp

- Added getMessageOp

- Added typedOpArg

- Added typedOp

- Added copyOp

- Added getInputChannelByIdOp

- Added getInputUserByIdOp

- Added getInputPeerByIdOp

- Added constructorOp

- Added vectorOp

- Added intLiteralOp

- Added longLiteralOp

- Added stringLiteralOp

- Added bytesLiteralOp

- Added boolLiteralOp

- Added doubleLiteralOp

- Added themeFormatLiteralOp

#### File reference map file schema »

#### File reference database schema » changes

##### New Constructors

- Added boolFalse - Constructor may be interpreted as a booleanfalse value.

- Added boolTrue - The constructor can be interpreted as a booleantrue value.

- Added true - See predefined identifiers.

- Added vector - A universal vector constructor.

- Added fileIdPhoto

- Added fileIdDocument

- Added fileSourceMessage

- Added fileSourceStarsTransaction

- Added fileSourceStory

- Added fileSourceWebPage

- Added fileSourceBotApp

- Added fileSourceUserFull

- Added fileSourceAdminLog

- Added fileSourceStoryAlbum

- Added fileSourceBotPreviewMedia

- Added fileSourceBotPreviewInfo

- Added fileSourcePaidMedia

- Added fileSourceSavedMusic

- Added fileSourceChatFull

- Added fileSourceChannelFull

- Added fileSourcePremiumPromo

- Added fileSourceAttachMenuBot

- Added fileSourceTheme

- Added fileSourceWallPaper

- Added fileSourceStickerSet

- Added fileSourceSavedGifs

- Added fileSourceSavedRingtones

- Added fileSourceAvailableEffects

- Added fileSourceAvailableReactions

- Added fileSourceUserProfilePhoto

- Added fileSourceDocumentByHash

#### File reference database schema »

#### Changes in the file reference database map file »

##### New Locations

- Added inputPhoto - fileIdPhoto (outgoing)

- Added inputDocument - fileIdDocument (outgoing)

- Added inputDocumentFileLocation - fileIdDocument (outgoing)

- Added inputPhotoFileLocation - fileIdPhoto (outgoing)

- Added document - fileIdDocument (incoming)

- Added photo - fileIdPhoto (incoming)

##### New Origins

- Added message - fileSourceMessage{from_scheduled: message.from_scheduled?passthrough, quick_reply_shortcut_id: message.quick_reply_shortcut_id?passthrough, peer: extractPeerIdFromPeerAndStore(message.peer_id), id: message.id}

- Added messageService - fileSourceMessage{peer: extractPeerIdFromPeerAndStore(messageService.peer_id), id: messageService.id, from_scheduled: false, quick_reply_shortcut_id: false}

- Added (1) storyItem - (needs stories.getPinnedStories) fileSourceStory{id: storyItem.id, peer: extractPeerIdFromInputPeerAndStore(stories.getPinnedStories.peer)}

- Added (2) storyItem - (needs stories.getStoriesArchive) fileSourceStory{id: storyItem.id, peer: extractPeerIdFromInputPeerAndStore(stories.getStoriesArchive.peer)}

- Added (3) storyItem - (needs stories.getStoriesByID) fileSourceStory{id: storyItem.id, peer: extractPeerIdFromInputPeerAndStore(stories.getStoriesByID.peer)}

- Added (4) storyItem - (needs stories.getAlbumStories) fileSourceStory{id: storyItem.id, peer: extractPeerIdFromInputPeerAndStore(stories.getAlbumStories.peer)}

- Added (5) storyItem - (needs peerStories) fileSourceStory{id: storyItem.id, peer: extractPeerIdFromPeerAndStore(peerStories.peer)}

- Added (6) storyItem - fileSourceStory{id: storyItem.id, peer: extractPeerIdFromPeerAndStore(storyItem.from_id?abort_if_empty)}

- Added storyViewPublicRepost - fileSourceStory{id: storyViewPublicRepost.story.storyItem.id, peer: extractPeerIdFromPeerAndStore(storyViewPublicRepost.peer_id)}

- Added storyReactionPublicRepost - fileSourceStory{id: storyReactionPublicRepost.story.storyItem.id, peer: extractPeerIdFromPeerAndStore(storyReactionPublicRepost.peer_id)}

- Added foundStory - fileSourceStory{id: foundStory.story.storyItem.id, peer: extractPeerIdFromPeerAndStore(foundStory.peer)}

- Added publicForwardStory - fileSourceStory{id: publicForwardStory.story.storyItem.id, peer: extractPeerIdFromPeerAndStore(publicForwardStory.peer)}

- Added webPageAttributeStory - fileSourceStory{id: webPageAttributeStory.story?abort_if_empty.storyItem.id, peer: extractPeerIdFromPeerAndStore(webPageAttributeStory.peer)}

- Added messageMediaStory - fileSourceStory{id: messageMediaStory.story?abort_if_empty.storyItem.id, peer: extractPeerIdFromPeerAndStore(messageMediaStory.peer)}

- Added webPage - fileSourceWebPage{url: webPage.url}

- Added botApp - fileSourceBotApp{id: botApp.id, access_hash: botApp.access_hash}

- Added botInfo - fileSourceUserFull{id: botInfo.user_id?abort_if_empty}

- Added channelAdminLogEvent - (needs channels.getAdminLog) fileSourceAdminLog{channel: extractChannelIdFromInputChannelAndStore(channels.getAdminLog.channel), max_id: channelAdminLogEvent.id}

- Added stories.createAlbum - fileSourceStoryAlbum{peer: extractPeerIdFromInputPeerAndStore(stories.createAlbum.peer)}

- Added stories.getAlbums - fileSourceStoryAlbum{peer: extractPeerIdFromInputPeerAndStore(stories.getAlbums.peer)}

- Added stories.updateAlbum - fileSourceStoryAlbum{peer: extractPeerIdFromInputPeerAndStore(stories.updateAlbum.peer)}

- Added bots.getPreviewMedias - fileSourceBotPreviewMedia{bot: extractUserIdFromInputUserAndStore(bots.getPreviewMedias.bot)}

- Added bots.getPreviewInfo - fileSourceBotPreviewInfo{bot: extractUserIdFromInputUserAndStore(bots.getPreviewInfo.bot), lang_code: bots.getPreviewInfo.lang_code}

- Added bots.addPreviewMedia - fileSourceBotPreviewInfo{bot: extractUserIdFromInputUserAndStore(bots.addPreviewMedia.bot), lang_code: bots.addPreviewMedia.lang_code}

- Added bots.editPreviewMedia - fileSourceBotPreviewInfo{bot: extractUserIdFromInputUserAndStore(bots.editPreviewMedia.bot), lang_code: bots.editPreviewMedia.lang_code}

- Added updateMessageExtendedMedia - fileSourcePaidMedia{id: updateMessageExtendedMedia.msg_id, peer: extractPeerIdFromPeerAndStore(updateMessageExtendedMedia.peer)}

- Added (1) userFull - fileSourceUserFull{id: userFull.id}

- Added (2) userFull - fileSourceSavedMusic{user_id: userFull.id, id: userFull.saved_music?abort_if_empty.document.id, access_hash: userFull.saved_music?abort_if_empty.document.access_hash}

- Added chatFull - fileSourceChatFull{chat_id: chatFull.id}

- Added channelFull - fileSourceChannelFull{channel: channelFull.id}

- Added help.getPremiumPromo - fileSourcePremiumPromo{}

- Added (1) starsTransaction - (needs payments.getStarsStatus) fileSourceStarsTransaction{peer: extractPeerIdFromInputPeerAndStore(payments.getStarsStatus.peer), ton: payments.getStarsStatus.ton?passthrough, id: starsTransaction.id, refund: starsTransaction.refund?passthrough}

- Added (2) starsTransaction - (needs payments.getStarsTransactions) fileSourceStarsTransaction{peer: extractPeerIdFromInputPeerAndStore(payments.getStarsTransactions.peer), ton: payments.getStarsTransactions.ton?passthrough, id: starsTransaction.id, refund: starsTransaction.refund?passthrough}

- Added (3) starsTransaction - (needs payments.getStarsTransactionsByID) fileSourceStarsTransaction{peer: extractPeerIdFromInputPeerAndStore(payments.getStarsTransactionsByID.peer), ton: payments.getStarsTransactionsByID.ton?passthrough, id: starsTransaction.id, refund: starsTransaction.refund?passthrough}

- Added (4) starsTransaction - (needs payments.getStarsSubscriptions) fileSourceStarsTransaction{peer: extractPeerIdFromInputPeerAndStore(payments.getStarsSubscriptions.peer), id: starsTransaction.id, refund: starsTransaction.refund?passthrough, ton: false}

- Added attachMenuBot - fileSourceAttachMenuBot{bot: attachMenuBot.bot_id}

- Added theme - fileSourceTheme{id: theme.id, access_hash: theme.access_hash}

- Added wallPaper - fileSourceWallPaper{id: wallPaper.id, access_hash: wallPaper.access_hash}

- Added stickerSetMultiCovered - fileSourceStickerSet{stickerset: extractInputStickerSetFromStickerSetAndStore(stickerSetMultiCovered.set)}

- Added stickerSetFullCovered - fileSourceStickerSet{stickerset: extractInputStickerSetFromStickerSetAndStore(stickerSetFullCovered.set)}

- Added messages.stickerSet - fileSourceStickerSet{stickerset: extractInputStickerSetFromStickerSetAndStore(messages.stickerSet.set)}

- Added messages.savedGifs - fileSourceSavedGifs{}

- Added account.savedRingtones - fileSourceSavedRingtones{}

- Added account.savedRingtoneConverted - fileSourceSavedRingtones{}

- Added account.uploadRingtone - fileSourceSavedRingtones{}

- Added messages.availableEffects - fileSourceAvailableEffects{}

- Added messages.availableReactions - fileSourceAvailableReactions{}

- Added photo - (needs photos.getUserPhotos) fileSourceUserProfilePhoto{user_id: extractUserIdFromInputUserAndStore(photos.getUserPhotos.user_id), max_id: photo.id}

- Added photos.updateProfilePhoto - fileSourceUserProfilePhoto{user_id: extractUserIdFromInputUserAndStore(photos.updateProfilePhoto.bot?fallback(inputUserSelf{})), max_id: photos.updateProfilePhoto.(return value).photos.photo.photo.photo.id}

- Added photos.uploadProfilePhoto - fileSourceUserProfilePhoto{user_id: extractUserIdFromInputUserAndStore(photos.uploadProfilePhoto.bot?fallback(inputUserSelf{})), max_id: photos.uploadProfilePhoto.(return value).photos.photo.photo.photo.id}

- Added photos.uploadContactProfilePhoto - fileSourceUserProfilePhoto{user_id: extractUserIdFromInputUserAndStore(photos.uploadContactProfilePhoto.user_id), max_id: photos.uploadContactProfilePhoto.(return value).photos.photo.photo.photo.id}

- Added (1) document - fileSourceStickerSet{stickerset: extractInputStickerSetFromDocumentAttributesAndStore(document.attributes)}

- Added (2) document - (needs users.getSavedMusic) fileSourceSavedMusic{user_id: extractUserIdFromInputUserAndStore(users.getSavedMusic.id), id: document.id, access_hash: document.access_hash}

- Added (3) document - (needs users.getSavedMusicByID) fileSourceSavedMusic{user_id: extractUserIdFromInputUserAndStore(users.getSavedMusicByID.id), id: document.id, access_hash: document.access_hash}

- Added messages.getDocumentByHash - fileSourceDocumentByHash{sha256: messages.getDocumentByHash.sha256, size: messages.getDocumentByHash.size, mime_type: messages.getDocumentByHash.mime_type}

##### New Skipped

- Added messages.getSponsoredMessages - Do not store file references from sponsored messages

- Added help.getAppUpdate - Don't handle file references from ephemeral app update info

- Added help.getRecentMeUrls - Don't handle file references from recent t.me URLs

- Added recentMeUrlChatInvite - Do not store references based on chat invite links

- Added messages.checkChatInvite - Do not store references based on chat invite links

- Added messages.getInlineBotResults - Inline bot results are ephemeral

- Added messages.getPreparedInlineMessage - Inline bot results are ephemeral

- Added messages.uploadMedia - A freshly uploaded media file will obtain a context only once it is sent to a chat

- Added messages.uploadImportedMedia - A freshly uploaded media file will obtain a context only once it is sent to a chat

- Added updateServiceNotification - Cannot refetch service notifications

- Added messages.getWebPagePreview - No locations are added for the method call, as it doesn't use persistent IDs as input; the location is instead extracted from the persistent IDs in the returned WebPage object

- Added payments.resaleStarGifts - Contexts for star gifts are not yet implemented

- Added payments.starGiftUpgradePreview - Contexts for star gifts are not yet implemented

- Added starGift - Contexts for star gifts are not yet implemented

- Added starGiftUnique - Contexts for star gifts are not yet implemented

- Added starGiftCollection - Contexts for star gifts are not yet implemented

- Added payments.starGiftCollections - Contexts for star gifts are not yet implemented

- Added messages.getCustomEmojiDocuments - Do not store file references in this context

- Added account.uploadTheme - A freshly uploaded theme file will obtain a context only once it is created via account.createTheme

##### New Actions

- Added fileSourceMessage - getMessageOp(peer: getInputPeerByIdOp(peer), id: copyOp(id), from_scheduled: copyOp(from_scheduled)quick_reply_shortcut_id: copyOp(quick_reply_shortcut_id))

- Added fileSourceStory - stories.getStoriesByID(id: [copyOp(id)], peer: getInputPeerByIdOp(peer))

- Added fileSourceWebPage - messages.getWebPage(url: copyOp(url), hash: 0)

- Added fileSourceBotApp - messages.getBotApp(app: inputBotAppID{id: copyOp(id), access_hash: copyOp(access_hash)}, hash: 0)

- Added fileSourceUserFull - users.getFullUser(id: getInputUserByIdOp(id))

- Added fileSourceAdminLog - channels.getAdminLog(channel: getInputChannelByIdOp(channel), max_id: copyOp(max_id), min_id: copyOp(max_id), limit: 1, q: "")

- Added fileSourceStoryAlbum - stories.getAlbums(peer: getInputPeerByIdOp(peer), hash: 0)

- Added fileSourceBotPreviewMedia - bots.getPreviewMedias(bot: getInputUserByIdOp(bot))

- Added fileSourceBotPreviewInfo - bots.getPreviewInfo(bot: getInputUserByIdOp(bot), lang_code: copyOp(lang_code))

- Added fileSourcePaidMedia - messages.getExtendedMedia(id: [copyOp(id)], peer: getInputPeerByIdOp(peer))

- Added fileSourceSavedMusic - users.getSavedMusicByID(id: getInputUserByIdOp(user_id), documents: [inputDocument{id: copyOp(id), access_hash: copyOp(access_hash), file_reference: base64_decode("")}])

- Added fileSourceChatFull - messages.getFullChat(chat_id: copyOp(chat_id))

- Added fileSourceChannelFull - channels.getFullChannel(channel: getInputChannelByIdOp(channel))

- Added fileSourcePremiumPromo - help.getPremiumPromo()

- Added fileSourceStarsTransaction - payments.getStarsTransactionsByID(peer: getInputPeerByIdOp(peer), ton: copyOp(ton), id: [inputStarsTransaction{id: copyOp(id), refund: copyOp(refund)}])

- Added fileSourceAttachMenuBot - messages.getAttachMenuBot(bot: getInputUserByIdOp(bot))

- Added fileSourceTheme - account.getTheme(theme: inputTheme{id: copyOp(id), access_hash: copyOp(access_hash)}, format: $themeFormat)

- Added fileSourceWallPaper - account.getWallPaper(wallpaper: inputWallPaper{id: copyOp(id), access_hash: copyOp(access_hash)})

- Added fileSourceStickerSet - messages.getStickerSet(stickerset: copyOp(stickerset), hash: 0)

- Added fileSourceSavedGifs - messages.getSavedGifs(hash: 0)

- Added fileSourceSavedRingtones - account.getSavedRingtones(hash: 0)

- Added fileSourceAvailableEffects - messages.getAvailableEffects(hash: 0)

- Added fileSourceAvailableReactions - messages.getAvailableReactions(hash: 0)

- Added fileSourceUserProfilePhoto - photos.getUserPhotos(user_id: getInputUserByIdOp(user_id), offset: -1, max_id: copyOp(max_id), limit: 1)

- Added fileSourceDocumentByHash - messages.getDocumentByHash(sha256: copyOp(sha256), size: copyOp(size), mime_type: copyOp(mime_type))

### Layer 213

This layer introduces the following new features:

- Changing the default profile tab »

- Saving music to the profile »

- Added a locked_until_date flag to starGift, for locked gifts that cannot be sent until the specified date.

- Added the payments.checkCanSendGift method, to check if a non-locked gift can't be sent yet for other reasons.

- Added an optional spend_purpose_peer flag to inputStorePaymentStarsTopup, that should be populated with the peer where the topup process was initiated due to low funds (i.e. a bot for bot payments, a channel for paid media/reactions, etc) »

Documentation for the profile page was also reorganized, to include the full list of tabs to show, along with instructions on how to populate them ».

#### Schema changes

##### New Methods

- Added account.setMainProfileTab - Changes the main profile tab of the current user, see here » for more info.

- Added account.saveMusic - Adds or removes a song from the current user's profile see here » for more info on the music tab of the profile page.

- Added account.getSavedMusicIds - Fetch the full list of only the IDs of songs currently added to the profile, see here » for more info.

- Added users.getSavedMusic - Get songs pinned to the user's profile, see here » for more info.

- Added users.getSavedMusicByID - Check if the passed songs are still pinned to the user's profile, or refresh the file references of songs pinned on a user's profile see here » for more info.

- Added channels.setMainProfileTab - Changes the main profile tab of a channel, see here » for more info.

- Added payments.checkCanSendGift - Check if the specified gift » can be sent.

##### New Constructors

- Added profileTabPosts - Represents the stories tab of a profile page.

- Added profileTabGifts - Represents the gifts tab of a profile page.

- Added profileTabMedia - Represents the media tab of a profile page.

- Added profileTabFiles - Represents the shared files tab of a profile.

- Added profileTabMusic - Represents the music tab of a profile page.

- Added profileTabVoice - Represents the voice messages tab of a profile page.

- Added profileTabLinks - Represents the shared links tab of a profile page.

- Added profileTabGifs - Represents the gifs tab of a profile page.

- Added users.savedMusicNotModified - This subset of the songs currently pinned on a user's profile hasn't changed, see here » for more info.

- Added users.savedMusic - List of songs currently pinned on a user's profile, see here » for more info.

- Added account.savedMusicIdsNotModified - The list of IDs of songs (document.ids) currently pinned on our profile hasn't changed.

- Added account.savedMusicIds - List of IDs of songs (document.ids) currently pinned on our profile, see here » for more info.

- Added payments.checkCanSendGiftResultOk - The specified gift can be sent.

- Added payments.checkCanSendGiftResultFail - The specified gift cannot be sent yet for the specified reason.

##### Changed Constructors

- Added main_tab parameter in channelFull

- Added upgrade_separate parameter in messageActionStarGift

- Added main_tab, saved_music parameters in userFull

- Added flags, spend_purpose_peer parameters in inputStorePaymentStarsTopup

- Added locked_until_date parameter in starGift

- Added chats parameter in payments.uniqueStarGift

- Added chats parameter in messages.webPagePreview

- Added upgrade_separate parameter in savedStarGift

#### Schema

### Layer 212

This layer introduces the following features:

- Separately prepay for the upgrade of a gift ».

- Get info about the value of a collectible gift »

#### Schema changes

##### New Methods

- Added payments.getUniqueStarGiftValueInfo - Get information about the value of a collectible gift ».

##### Changed Methods

- Added exclude_upgradable, exclude_unupgradable parameters, removed exclude_limited parameter in payments.getSavedStarGifts

##### New Constructors

- Added inputInvoiceStarGiftPrepaidUpgrade - Separately prepay for the upgrade of a gift ».

- Added payments.uniqueStarGiftValueInfo - Information about the value of a collectible gift ».

##### Changed Constructors

- Added prepaid_upgrade, prepaid_upgrade_hash, gift_msg_id parameters in messageActionStarGift

- Added prepaid_upgrade parameter in messageActionStarGiftUnique

- Added posts_search, stargift_prepaid_upgrade parameters in starsTransaction

- Added gift_id, value_amount, value_currency parameters in starGiftUnique

- Added prepaid_upgrade_hash parameter in savedStarGift

#### Schema

### Layer 211

This layer introduces:

- Story albums »

- Star gift collection link previews »

- Full text global channel post search »

- Allow specification of the resale price of a collectible gift in TON »

- Pending star ratings »

#### Schema changes

##### New Methods

- Added channels.checkSearchPostsFlood - Check if the specified global post search » requires payment.

- Added stories.createAlbum - Creates a story album.

- Added stories.updateAlbum - Rename a story albums », or add, delete or reorder stories in it.

- Added stories.reorderAlbums - Reorder story albums on a profile ».

- Added stories.deleteAlbum - Delete a story album.

- Added stories.getAlbums - Get story albums created by a peer.

- Added stories.getAlbumStories - Get stories in a story album ».

##### Changed Methods

- Added flags, query, allow_paid_stars parameters, changed type of hashtag from string to flags.0?string in channels.searchPosts

- Added resell_amount parameter, removed resell_stars parameter in payments.updateStarGiftPrice

- Added albums parameter in stories.sendStory

##### New Constructors

- Added webPageAttributeStarGiftCollection - Contains info about a gift collection » for a webPage preview of a gift collection » (the webPage will have a type of telegram_collection).

- Added storyAlbum - Represents a story album ».

- Added stories.albumsNotModified - The story album list » hasn't changed.

- Added stories.albums - Story albums ».

- Added searchPostsFlood - Indicates if the specified global post search » requires payment.

##### Changed Constructors

- Added resale_amount parameter, removed resale_stars parameter in messageActionStarGiftUnique

- Added stars_my_pending_rating, stars_my_pending_rating_date parameters in userFull

- Added search_flood parameter in messages.messagesSlice

- Added flags, ton parameters in inputInvoiceStarGiftResale

- Added albums parameter in storyItem

- Added resale_ton_only, resell_amount parameters, removed resell_stars parameter in starGiftUnique

#### Schema

### Layer 210

This layer introduces:

- Star gift collections »

- Premium-only gifts (require_premium) and per-user gift limits for certain gift types (per_user_total, per_user_remains).

- Star ratings »

#### Schema changes

##### New Methods

- Added payments.createStarGiftCollection - Create a star gift collection ».

- Added payments.updateStarGiftCollection - Add or remove gifts from a star gift collection », or rename the collection.

- Added payments.reorderStarGiftCollections - Reorder the star gift collections » on an owned peer's profile.

- Added payments.deleteStarGiftCollection - Delete a star gift collection ».

- Added payments.getStarGiftCollections - Fetches all star gift collections » of a peer.

##### Changed Methods

- Added collection_id parameter in payments.getSavedStarGifts

##### New Constructors

- Added starsRating - Represents the profile's star rating, see here » for more info.

- Added starGiftCollection - Represents a star gift collection ».

- Added payments.starGiftCollectionsNotModified - The list of star gift collections » hasn't changed.

- Added payments.starGiftCollections - Represents a list of star gift collections ».

##### Changed Constructors

- Added stars_rating parameter in userFull

- Added require_premium, limited_per_user, per_user_total, per_user_remains parameters in starGift

- Added require_premium parameter in starGiftUnique

- Added collection_id parameter in savedStarGift

#### Schema

### Layer 208

This layer introduces:

- Suggested channel posts »

- Add a new manage_direct_messages admin right

- Add support for the new manage_direct_messages admin right in group/channel bot links

- Allow replying to specific todo tasks »

- Unify channel revenue statistics and withdrawal methods with the equivalent ones used for stars, by simply adding a ton flag and the missing parameters:

- Balance and transaction history »

- Revenue statistics »

- Withdrawing revenue »

- In some places in the API, it's possible to use toncoins instead of Stars, see here » for more info.

#### Schema changes

##### New Methods

- Added messages.toggleSuggestedPostApproval - Approve or reject a suggested post ».

##### Changed Methods

- Added suggested_post parameter in messages.sendMessage

- Added suggested_post parameter in messages.sendMedia

- Added suggested_post parameter in messages.forwardMessages

- Added suggested_post parameter in messages.saveDraft

- Added flags, ton parameters in payments.getStarsStatus

- Added ton parameter in payments.getStarsTransactions

- Added ton parameter in payments.getStarsRevenueStats

- Added flags, ton, amount parameters, removed stars parameter in payments.getStarsRevenueWithdrawalUrl

- Added flags, ton parameters in payments.getStarsTransactionsByID

##### Deleted Methods

- Removed stats.getBroadcastRevenueStats

- Removed stats.getBroadcastRevenueWithdrawalUrl

- Removed stats.getBroadcastRevenueTransactions

##### New Constructors

- Added suggestedPost - Contains info about a suggested post ».

- Added messageActionSuggestedPostApproval - A suggested post » was approved or rejected.

- Added messageActionSuggestedPostSuccess - A suggested post » was successfully posted, and payment for it was successfully received.

- Added messageActionSuggestedPostRefund - A suggested post » was accepted and posted or scheduled, but either the channel deleted the posted/scheduled post before stars_suggested_post_age_min seconds have elapsed, or the user refunded the payment for the stars used to pay for the suggested post.

- Added starsTonAmount - Describes an amount of toncoin in nanotons (i.e. 1/1_000_000_000 of a toncoin).

- Added messageActionGiftTon - You were gifted some toncoins.

- Added inputStickerSetTonGifts - TON gifts stickerset.

##### Changed Constructors

- Added paid_suggested_post_stars, paid_suggested_post_ton, suggested_post parameters in message

- Added suggested_post parameter in draftMessage

- Added manage_direct_messages parameter in chatAdminRights

- Added todo_item_id parameter in messageReplyHeader

- Added todo_item_id parameter in inputReplyToMessage

- Added amount, ads_proceeds_from_date, ads_proceeds_to_date parameters, removed stars parameter in starsTransaction

- Added flags, top_hours_graph parameters in payments.starsRevenueStats

- Added released_by parameter in starGift

- Added chats, users parameters in payments.starGifts

- Added released_by parameter in starGiftUnique

##### Deleted Constructors

- Removed stats.broadcastRevenueStats

- Removed stats.broadcastRevenueWithdrawalUrl

- Removed broadcastRevenueTransactionProceeds

- Removed broadcastRevenueTransactionWithdrawal

- Removed broadcastRevenueTransactionRefund

- Removed stats.broadcastRevenueTransactions

- Removed broadcastRevenueBalances

- Removed updateBroadcastRevenueTransactions

#### Schema

### Layer 205

This layer introduces:

- Sponsored messages to show on channel videos »

- To-do lists »

- Rename account.addNoPaidMessagesException to account.toggleNoPaidMessagesException, and add a require_payment flag to refund all Stars transferred to us by a peer with paid messages »

- Allow invoking account.toggleNoPaidMessagesException for monoforum topics, and add a new updateMonoForumNoPaidException to signal changes to monoForumDialog.nopaid_messages_exception to other admins and to other currently logged in sessions of the current monoforum admin.

#### Schema changes

##### New Methods

- Added messages.toggleTodoCompleted - Mark one or more items of a todo list » as completed or not completed.

- Added messages.appendTodoList - Appends one or more items to a todo list ».

- Added account.toggleNoPaidMessagesException - Allow a user to send us messages without paying if paid messages » are enabled.

##### Changed Methods

- Added flags, msg_id parameters in messages.getSponsoredMessages

- Added flags, parent_peer parameters in account.getPaidMessagesRevenue

##### Deleted Methods

- Removed account.addNoPaidMessagesException

##### New Constructors

- Added todoItem - An item of a todo list ».

- Added todoList - Represents a todo list ».

- Added todoCompletion - A completed todo list » item.

- Added inputMediaTodo - Creates a todo list ».

- Added messageMediaToDo - Represents a todo list ».

- Added messageActionTodoCompletions - Items were marked as completed or not completed in a todo list ».

- Added messageActionTodoAppendTasks - Items were appended to the todo list ».

- Added updateMonoForumNoPaidException - An admin has (un)exempted this monoforum topic » from payment to send messages using account.toggleNoPaidMessagesException.

##### Changed Constructors

- Added saved_peer_id parameter in messageService

- Added send_paid_messages_stars parameter in channelFull

- Added min_display_duration, max_display_duration parameters in sponsoredMessage

- Added start_delay, between_delay parameters in messages.sponsoredMessages

- Added nopaid_messages_exception parameter in monoForumDialog

#### PUSH notification changes

##### New PUSH notifications

- Added CHANNEL_MESSAGE_TODO - {1} posted a checklist {2}

- Added CHANNEL_MESSAGE_TODO_APPEND - {1} added {2} tasks

- Added CHANNEL_MESSAGE_TODO_DONE - {1} toggled {2} tasks

- Added CHAT_MESSAGE_TODO - {1} sent a checklist {3} to the group {2}

- Added CHAT_MESSAGE_TODO_APPEND - {1} added {3} tasks in the group {2}

- Added CHAT_MESSAGE_TODO_DONE - {1} toggled {3} tasks in the group {2}

- Added CHAT_REACT_TODO - {1}: {3} to your checklist {4} in {2}

- Added MESSAGE_TODO - {1} sent you a checklist {2}

- Added PINNED_TODO - {1} pinned a checklist {2}

- Added REACT_TODO - {1}: {2} to your checklist {3}

#### Schema

### Layer 204

This layer introduces:

- Monoforums »

- Bot API monoforum IDs »

- Tabbed forum UI »

- All flags added to channel (listed below) are valid min flags, meaning they will must be applied over the locally stored version even if the min flag of the incoming channel is set.

#### Schema changes

##### New Methods

- Added messages.getSavedDialogsByID - Obtain information about specific saved message dialogs » or monoforum topics ».

- Added messages.readSavedHistory - Mark messages as read in a monoforum topic ».

- Added channels.getMessageAuthor - Can only be invoked by non-bot admins of a monoforum », obtains the original sender of a message sent by other monoforum admins to the monoforum, on behalf of the channel associated to the monoforum.

##### Changed Methods

- Added reply_to parameter in messages.forwardMessages

- Added parent_peer parameter in messages.markDialogUnread

- Added flags, parent_peer parameters in messages.getDialogUnreadMarks

- Added saved_peer_id parameter in messages.unpinAllMessages

- Added saved_peer_id parameter in messages.getUnreadReactions

- Added saved_peer_id parameter in messages.readReactions

- Added tabs parameter in channels.toggleForum

- Added parent_peer parameter in messages.getSavedDialogs

- Added flags, parent_peer parameters in messages.getSavedHistory

- Added parent_peer parameter in messages.deleteSavedHistory

- Added flags, broadcast_messages_allowed parameters in channels.updatePaidMessagesPrice

##### New Constructors

- Added inputReplyToMonoForum - Used to send messages to a monoforum topic.

- Added monoForumDialog - Represents a monoforum topic ».

- Added updateReadMonoForumInbox - Incoming messages in a monoforum topic were read

- Added updateReadMonoForumOutbox - Outgoing messages in a monoforum were read.

##### Changed Constructors

- Added broadcast_messages_allowed, monoforum, forum_tabs, linked_monoforum_id parameters in channel

- Added saved_peer_id parameter in updateDraftMessage

- Added saved_peer_id parameter in updateChannelReadMessagesContents

- Added saved_peer_id parameter in updateDialogUnreadMark

- Added saved_peer_id parameter in updateMessageReactions

- Added monoforum_peer_id parameter in inputReplyToMessage

- Added flags, broadcast_messages_allowed parameters in messageActionPaidMessagesPrice

#### Schema

### Layer 203

This layer introduces:

- Methods to resell collectible gifts »

- Autotranslation for all users of a channel »

- stories.canSendStory now returns the number of available active story slots »

- Collectible gift links »

- Custom suggestions »

- All suggestion fields were moved from the client configuration object to help.getPromoData »

- All flags added to channel (listed below) are valid min flags, meaning they will must be applied over the locally stored version even if the min flag of the incoming channel is set.

#### Schema changes

##### New Methods

- Added payments.getResaleStarGifts - Get collectible gifts of a specific type currently on resale, see here » for more info.

- Added payments.updateStarGiftPrice - A collectible gift we own » can be put up for sale on the gift marketplace » with this method, see here » for more info.

- Added channels.toggleAutotranslation - Toggle autotranslation in a channel, for all users: see here » for more info.

##### Changed Methods

- Changed type of stories.canSendStory from Bool to stories.CanSendStoryCount

##### New Constructors

- Added inputSavedStarGiftSlug - Points to a collectible gift obtained from a collectible gift link ».

- Added starGiftAttributeIdModel - The ID of a model of a collectible gift ».

- Added starGiftAttributeIdPattern - The ID of a pattern of a collectible gift ».

- Added starGiftAttributeIdBackdrop - The ID of a backdrop of a collectible gift ».

- Added starGiftAttributeCounter - Indicates the total number of gifts that have the specified attribute.

- Added payments.resaleStarGifts - List of gifts currently on resale ».

- Added inputInvoiceStarGiftResale - Used to buy a collectible gift currently up on resale, see here for more info on the full flow.

- Added channelAdminLogEventActionToggleAutotranslation - Channel autotranslation was toggled ».

- Added stories.canSendStoryCount - Contains the number of available active story slots (equal to the value of the story_expiring_limit_* client configuration parameter minus the number of currently active stories).

- Added pendingSuggestion - Represents a custom pending suggestion ».

##### Changed Constructors

- Added autotranslation parameter in channel

- Added pending_suggestions, dismissed_suggestions, custom_pending_suggestion parameters, changed type of peer from Peer to flags.3?Peer in help.promoData

- Added availability_resale, resell_min_stars, title parameters in starGift

- Added backdrop_id parameter in starGiftAttributeBackdrop

- Added resell_stars parameter in starGiftUnique

- Added resale_stars, can_transfer_at, can_resell_at parameters in messageActionStarGiftUnique

- Added can_transfer_at, can_resell_at parameters in savedStarGift

#### Schema

### Layer 202

This layer introduces:

- End-to-end group calls »

- Conference deep links »

- Service messages for paid message refunds »

- Service messages for paid message price changes »

- Gift privacy settings:

- globalPrivacySettings.disallowed_gifts/userFull.disallowed_gifts: Disallow the reception of specific gift types »

- globalPrivacySettings.display_gifts_button/userFull.display_gifts_button: show or hide the gift button in the text field of private chats.

- Transferring stars from a business account to the business bot »

- Sponsored peer search results »

- Business bot rights »

- Sponsored message methods now don't require specification of the peer where the sponsored message is visible »

- Renamed the method used by official apps to check whether an in-store purchase is possible »

- Paid auth codes for official apps

#### Schema changes

##### New Methods

- Added payments.canPurchaseStore - Checks whether a purchase is possible. Must be called before in-store purchase, official apps only.

- Added contacts.getSponsoredPeers - Obtain a list of sponsored peer search results for a given query

- Added phone.deleteConferenceCallParticipants - Remove participants from a conference call.

- Added phone.sendConferenceCallBroadcast - Broadcast a blockchain block to all members of a conference call, see here » for more info.

- Added phone.inviteConferenceCallParticipant - Invite a user to a conference call.

- Added phone.declineConferenceCallInvite - Declines a conference call invite.

- Added phone.getGroupCallChainBlocks - Fetch the blocks of a conference blockchain ».

##### Changed Methods

- Removed conference_call parameter in phone.requestCall

- Added public_key, block parameters, removed key_fingerprint parameter in phone.joinGroupCall

- Added rights parameter, removed can_reply parameter in account.updateConnectedBot

- Removed peer parameter in messages.viewSponsoredMessage

- Removed peer parameter in messages.clickSponsoredMessage

- Removed peer parameter in messages.reportSponsoredMessage

- Changed type of phone.createConferenceCall from phone.PhoneCall to Updates

- Added flags, muted, video_stopped, join, random_id, public_key, block, params parameters, removed peer, key_fingerprint parameters in phone.createConferenceCall

##### Deleted Methods

- Removed payments.canPurchasePremium

##### New Constructors

- Added auth.sentCodePaymentRequired - Official apps may receive this constructor, indicating that due to the high cost of SMS verification codes for the user's country/provider, the user must purchase a Telegram Premium subscription in order to proceed with the login/signup.

- Added inputStorePaymentAuthCode - Indicates payment for a login code.

- Added updateSentPhoneCode - A paid login SMS code was successfully sent.

- Added businessBotRights - Business bot rights.

- Added messageActionPaidMessagesRefunded - Sent from peer A to B, indicates that A refunded all stars B previously paid to send messages to A, see here » for more info on paid messages.

- Added messageActionPaidMessagesPrice - The price of paid messages » in this chat was changed.

- Added disallowedGiftsSettings - Disallow the reception of specific gift types.

- Added sponsoredPeer - A sponsored peer.

- Added contacts.sponsoredPeersEmpty - There are no sponsored peers for this query.

- Added contacts.sponsoredPeers - Sponsored peers.

- Added inputInvoiceBusinessBotTransferStars - Transfer stars from the balance of a user account connected to a business bot, to the balance of the business bot, see here » for more info on the full flow.

- Added inputGroupCallSlug - Join a conference call through an invitation link ».

- Added inputGroupCallInviteMessage - Join a group call through a messageActionConferenceCall invitation message.

- Added updateGroupCallChainBlocks - Contains updates to the blockchain of a conference call, see here » for more info.

- Added messageActionConferenceCall - Represents a conference call (or an invitation to a conference call, if neither the missed nor active flags are set).

- Added phoneCallDiscardReasonMigrateConferenceCall - This phone call was migrated to a conference call.

##### Changed Constructors

- Added display_gifts_button, disallowed_gifts parameters in userFull

- Removed conference_call parameter in phoneCallWaiting

- Removed conference_call parameter in phoneCallRequested

- Removed conference_call parameter in phoneCallAccepted

- Added conference_supported parameter, removed conference_call parameter in phoneCall

- Removed conference_call parameter in phoneCallDiscarded

- Added display_gifts_button, disallowed_gifts parameters in globalPrivacySettings

- Added conference, creator, invite_link parameters, removed conference_from_call parameter in groupCall

- Added rights parameter, removed can_reply parameter in connectedBot

- Added rights parameter, removed can_reply parameter in botBusinessConnection

#### PUSH notification changes

##### New PUSH notifications

- Added CONF_CALL_MISSED - You missed a call from {1}

#### Schema

### Layer 200

This layer introduces:

- Detailed account information for new private chats »

- Paid messages »

- Pinning a specific received gift to the profile »

- Sending paid reactions as a channel »

- Added a paid_messages_available flag to channelFull, indicating whether paid messages can be enabled in this supergroup

- Gift a Telegram Premium subscription, paying with Telegram Stars »

- This change also simplifies the Telegram Premium gift flow, fully replacing the userFull.premium_gifts flag with payments.getPremiumGiftCodeOptions.

- Blockchain addresses for collectible gifts moved to the TON blockchain as NFTs »

- All flags added to channel (listed below) are valid min flags, meaning they will must be applied over the locally stored version even if the min flag of the incoming channel is set.

- All flags added to user (listed below) are valid min flags, meaning they will must be applied over the locally stored version even if the min flag of the incoming user is set.

#### Schema changes

##### New Methods

- Added invokeWithReCaptcha - Official clients only: re-execute a method call that required reCAPTCHA verification via a RECAPTCHA_CHECK_%s__%s, where the first placeholder is the action, and the second one is the reCAPTCHA key ID.

- Added account.addNoPaidMessagesException

- Added account.getPaidMessagesRevenue - Get the number of stars we have received from the specified user thanks to paid messages »; the received amount will be equal to the sent amount multiplied by stars_paid_message_commission_permille divided by 1000.

- Added channels.updatePaidMessagesPrice - Enable or disable paid messages » in this supergroup or monoforum.

- Added users.getRequirementsToContact - Check whether we can write to the specified users, used to implement bulk checks for Premium-only messages » and paid messages ».

- Added payments.toggleStarGiftsPinnedToTop - Pins a received gift on top of the profile of the user or owned channels by using payments.toggleStarGiftsPinnedToTop.

##### Changed Methods

- Added allow_paid_stars parameter in messages.sendMessage

- Added allow_paid_stars parameter in messages.sendMedia

- Added allow_paid_stars parameter in messages.forwardMessages

- Added allow_paid_stars parameter in messages.sendInlineBotResult

- Added allow_paid_stars parameter in messages.sendMultiMedia

- Added flags, for_paid_reactions parameters in channels.getSendAs

- Changed type of private from flags.0?Bool to flags.0?PaidReactionPrivacy in messages.sendPaidReaction

- Changed type of private from Bool to PaidReactionPrivacy in messages.togglePaidReactionPrivacy

##### Deleted Methods

- Removed users.getIsPremiumRequiredToContact

##### New Constructors

- Added paidReactionPrivacyDefault - Uses the default reaction privacy, set using messages.togglePaidReactionPrivacy.

- Added paidReactionPrivacyAnonymous - Send paid reactions anonymously.

- Added paidReactionPrivacyPeer - Send paid reactions as the specified peer, fetched using channels.getSendAs.

- Added inputPrivacyKeyNoPaidMessages - Who can send you messages without paying, if paid messages » are enabled.

- Added privacyKeyNoPaidMessages - Who can send you messages without paying, if paid messages » are enabled.

- Added account.paidMessagesRevenue - Total number of non-refunded Telegram Stars a user has spent on sending us messages either directly or through a channel, see here » for more info on paid messages.

- Added requirementToContactEmpty - This user can be freely contacted.

- Added requirementToContactPremium - This user requires us to buy a Premium subscription in order to contact them.

- Added requirementToContactPaidMessages - This user requires us to pay the specified amount of Telegram Stars to send them a message, see here » for the full flow.

- Added inputInvoicePremiumGiftStars - Used to gift a Telegram Premium subscription to another user, paying with Telegram Stars.

##### Changed Constructors

- Added paid_message_stars parameter in message

- Added charge_paid_message_stars, registration_month, phone_country, name_change_date, photo_change_date parameters in peerSettings

- Added send_paid_messages_stars parameter, removed premium_gifts parameter in userFull

- Added send_paid_messages_stars parameter in user

- Added send_paid_messages_stars parameter in channel

- Added paid_messages_available parameter in channelFull

- Added noncontact_peers_paid_stars parameter in globalPrivacySettings

- Added business_transfer, stargift_resale, paid_messages, premium_gift_months parameters in starsTransaction

- Changed type of private from Bool to PaidReactionPrivacy in updatePaidReactionPrivacy

- Added gift_address parameter in starGiftUnique

##### Deleted Constructors

- Removed premiumGiftOption

#### Schema

### Layer 198

This layer introduces:

- Collectibles as emoji statuses (and minor tweaks to the emoji status API) »

- Send gifts to channels

- Notifications for gifts received by channels »

- Get all gifts received by a peer »

- Fetch info about specific gifts owned by a peer we control »

- Withdraw a collectible gift to the TON blockchain »

- Custom video covers »

- Custom starting timestamps for videos »

#### Schema changes

##### New Methods

- Added account.getCollectibleEmojiStatuses - Obtain a list of emoji statuses » for owned collectible gifts.

- Added payments.getSavedStarGifts - Fetch the full list of gifts owned by a peer.

- Added payments.getSavedStarGift - Fetch info about specific gifts owned by a peer we control.

- Added payments.getStarGiftWithdrawalUrl - Convert a collectible gift » to an NFT on the TON blockchain.

- Added payments.toggleChatStarGiftNotifications - Enables or disables the reception of notifications every time a gift » is received by the specified channel, can only be invoked by admins with post_messages admin rights.

##### Changed Methods

- Added video_timestamp parameter in messages.forwardMessages

- Added stargift parameter, removed msg_id parameter in payments.saveStarGift

- Added stargift parameter, removed msg_id parameter in payments.convertStarGift

- Added stargift parameter, removed msg_id parameter in payments.upgradeStarGift

- Added stargift parameter, removed msg_id parameter, changed type of to_id from InputUser to InputPeer in payments.transferStarGift

##### Deleted Methods

- Removed payments.getUserStarGifts

- Removed payments.getUserStarGift

##### New Constructors

- Added emojiStatusCollectible - An owned collectible gift » as emoji status.

- Added inputEmojiStatusCollectible - An owned collectible gift » as emoji status: can only be used in account.updateEmojiStatus, is never returned by the API.

- Added savedStarGift - Represents a gift owned by a peer.

- Added payments.savedStarGifts - Represents a list of gifts.

- Added inputSavedStarGiftUser - A gift received in a private chat with another user.

- Added inputSavedStarGiftChat - A gift received by a channel we own.

- Added payments.starGiftWithdrawalUrl - A URL that can be used to import the exported NFT on Fragment.

##### Changed Constructors

- Added video_cover, video_timestamp parameters in inputMediaUploadedDocument

- Added video_cover, video_timestamp parameters in inputMediaDocument

- Added video_cover, video_timestamp parameters in messageMediaDocument

- Added stargifts_available, stargifts_count parameters in channelFull

- Added video_cover, video_timestamp parameters in inputMediaDocumentExternal

- Added flags, until parameters in emojiStatus

- Added peer parameter, removed user_id parameter in inputInvoiceStarGift

- Added from_id, peer, saved_id parameters in messageActionStarGift

- Changed type of sender_id from flags.0?long to flags.0?Peer, recipient_id from long to Peer in starGiftAttributeOriginalDetails

- Added owner_address parameter, changed type of owner_id from flags.0?long to flags.0?Peer in starGiftUnique

- Added from_id, peer, saved_id parameters in messageActionStarGiftUnique

- Added stargift parameter, removed msg_id parameter in inputInvoiceStarGiftUpgrade

- Added stargift parameter, removed msg_id parameter, changed type of to_id from InputUser to InputPeer in inputInvoiceStarGiftTransfer

##### Deleted Constructors

- Removed emojiStatusUntil

- Removed userStarGift

- Removed payments.userStarGifts

#### Schema

### Layer 197

This layer introduces:

- Collectible gift links »

- Collectible gift story media areas »

- Collectible webpage previews »

- Similar bot recommendations »

#### Schema changes

##### New Methods

- Added bots.getBotRecommendations - Obtain a list of similarly themed bots, selected based on similarities in their subscriber bases, see here » for more info.

- Added payments.getUniqueStarGift - Obtain info about a collectible gift » using a slug obtained from a collectible gift link ».

##### Changed Methods

- Changed type of messages.getWebPagePreview from MessageMedia to messages.WebPagePreview

##### New Constructors

- Added users.users - Describes a list of users (or bots).

- Added users.usersSlice - Describes a partial list of users.

- Added payments.uniqueStarGift - Represents a collectible gift ».

- Added webPageAttributeUniqueStarGift - Contains info about collectible gift » for a webPage preview of a collectible gift » (the webPage will have a type of telegram_nft).

- Added mediaAreaStarGift - Represents a collectible gift ».

- Added messages.webPagePreview - Represents a webpage preview.

##### Changed Constructors

- Added flags, slug, owner_name parameters, changed type of owner_id from long to flags.0?long in starGiftUnique

#### Schema

### Layer 196

This layer introduces:

- Extra secure group calls »

- Explicit delivery acknowledgement for Telegram Gateway verification messages ».

- Third-party verification »

- Reactions for service messages »

- Collectible gifts »

- Add support for entities in folder titles, and a new title_noanimate flag to optionally freeze animated emoji entities in the title.

- All flags added to channel (listed below) are valid min flags, meaning they will must be applied over the locally stored version even if the min flag of the incoming channel is set.

- All flags added to user (listed below) are valid min flags, meaning they will must be applied over the locally stored version even if the min flag of the incoming user is set.

#### Schema changes

##### New Methods

- Added phone.createConferenceCall - Create and optionally join a new conference call.

- Added messages.reportMessagesDelivery - Used for Telegram Gateway verification messages »: indicate to the server that one or more messages were received by the client, if requested by the message.report_delivery_until_date flag or the equivalent flag in push notifications.

- Added bots.setCustomVerification - Verify a user or chat on behalf of an organization ».

- Added payments.getStarGiftUpgradePreview - Obtain a preview of the possible attributes (chosen randomly) a gift » can receive after upgrading it to a collectible gift », see here » for more info.

- Added payments.upgradeStarGift - Upgrade a gift to a collectible gift: can only be used if the upgrade was already paid by the gift sender; see here » for more info on the full flow (including the different flow to use in case the upgrade was not paid by the gift sender).

- Added payments.transferStarGift - Transfer a collectible gift to another user or channel: can only be used if transfer is free (i.e. messageActionStarGiftUnique.transfer_stars is not set); see here » for more info on the full flow (including the different flow to use in case the transfer isn't free).

- Added payments.getUserStarGift

##### Changed Methods

- Added conference_call parameter in phone.requestCall

- Added key_fingerprint parameter in phone.joinGroupCall

- Removed user_id parameter in payments.saveStarGift

- Removed user_id parameter in payments.convertStarGift

##### New Constructors

- Added botVerifierSettings - Info about the current verifier bot ».

- Added botVerification - Describes a bot verification icon ».

- Added starGiftAttributeModel - The model of a collectible gift ».

- Added starGiftAttributePattern - A sticker applied on the backdrop of a collectible gift » using a repeating pattern.

- Added starGiftAttributeBackdrop - The backdrop of a collectible gift ».

- Added starGiftAttributeOriginalDetails - Info about the sender, receiver and message attached to the original gift », before it was upgraded to a collectible gift ».

- Added starGiftUnique - Represents a collectible star gift, see here » for more info.

- Added messageActionStarGiftUnique - A gift » was upgraded to a collectible gift ».

- Added inputInvoiceStarGiftUpgrade - Used to pay to upgrade a Gift to a collectible gift, see the collectible gifts » documentation for more info on the full flow.

- Added inputInvoiceStarGiftTransfer - Used to pay to transfer a collectible gift to another peer, see the gifts » documentation for more info.

- Added payments.starGiftUpgradePreview - A preview of the possible attributes (chosen randomly) a gift » can receive after upgrading it to a collectible gift », see here » for more info.

##### Changed Constructors

- Added report_delivery_until_date parameter in message

- Added reactions_are_possible, reactions parameters in messageService

- Added bot_verification parameter in userFull

- Added video_cover_photo parameter in webPage

- Added bot_verification parameter in chatInvite

- Added bot_verification_icon parameter in user

- Added verifier_settings parameter in botInfo

- Added bot_verification_icon parameter in channel

- Added bot_verification parameter in channelFull

- Added conference_call parameter in phoneCallWaiting

- Added conference_call parameter in phoneCallRequested

- Added conference_call parameter in phoneCallAccepted

- Added conference_call parameter in phoneCall

- Added conference_call parameter in phoneCallDiscarded

- Added title_noanimate parameter, changed type of title from string to TextWithEntities in dialogFilter

- Added conference_from_call parameter in groupCall

- Added flags parameter, changed type of chat_id from long to flags.0?long in updateGroupCall

- Added title_noanimate parameter, changed type of title from string to TextWithEntities in dialogFilterChatlist

- Added title_noanimate parameter, changed type of title from string to TextWithEntities in chatlists.chatlistInvite

- Changed type of unclaimed from flags.2?true to flags.5?true in messageActionGiftCode

- Added stargift_upgrade parameter in starsTransaction

- Added upgrade_stars parameter in starGift

- Added include_upgrade parameter in inputInvoiceStarGift

- Added upgraded, refunded, can_upgrade, upgrade_msg_id, upgrade_stars parameters in messageActionStarGift

- Added refunded, can_upgrade, upgrade_stars, can_export_at, transfer_stars parameters in userStarGift

#### PUSH notification changes

##### New PUSH notifications

- Added MESSAGE_STARGIFT_UPGRADE - {1} upgraded your Gift

- Added MESSAGE_UNIQUE_STARGIFT - {1} transferred you a Gift!

#### Schema

### Layer 195

Start reading the changelog at layer 186 to view all changes since the last refresh of the documentation.

This layer introduces the following new features:

- Affiliate programs for bots »

- This includes the following new client configuration keys »

- starref_start_param_prefixes »

- starref_program_allowed »

- starref_connect_allowed »

- starref_min_commission_permille »

- starref_max_commission_permille »

- And the following new deep links:

- Referral links »

- AI-powered sticker search »

- A new USERPIC_SETUP suggestion » was added.

- The RPC error database was updated »

The following documentation was added for pre-existing features:

- Documentation was added for the following pre-existing client configuration keys »:

- inapp_update_check_delay »

- premium_manage_subscription_url »

- ignore_restriction_reasons »

- restriction_add_platforms »

- new_noncontact_peers_require_premium_without_ownpremium »

- The client configuration page » now contains the exact and full list of defaults for all configuration keys in JSON format (previously, the JSON dump only contained example values that couldn't all be used as valid defaults).

- Added documentation about Telegram Premium story feature identifiers »

- Added documentation about Telegram Premium limit feature identifiers »

- Updated the list of webPage types »

- Added info on how to handle ENCRYPTED_MESSAGE_INVALID errors while binding the auth key.

#### Schema changes

##### New Methods

- Added bots.getAdminedBots - Get a list of bots owned by the current user

- Added bots.updateStarRefProgram - Create, edit or delete the affiliate program of a bot we own

- Added payments.getConnectedStarRefBots - Fetch all affiliations we have created for a certain peer

- Added payments.getConnectedStarRefBot - Fetch info about a specific bot affiliation »

- Added payments.getSuggestedStarRefBots - Obtain a list of suggested mini apps with available affiliate programs

- Added payments.connectStarRefBot - Join a bot's affiliate program, becoming an affiliate »

- Added payments.editConnectedStarRefBot - Leave a bot's affiliate program »

- Added messages.searchStickers - Search for stickers using AI-powered keyword search

##### Changed Methods

- Added flags, referer parameters in contacts.resolveUsername

##### New Constructors

- Added starRefProgram - Indo about an affiliate program offered by a bot

- Added connectedBotStarRef - Info about an active affiliate program we have with a Mini App

- Added payments.connectedStarRefBots - Active affiliations

- Added payments.suggestedStarRefBots - A list of suggested mini apps with available affiliate programs

- Added starsAmount - Describes a real (i.e. possibly decimal) amount of Telegram Stars.

- Added messages.foundStickersNotModified - No new stickers were found for the specified query

- Added messages.foundStickers - Found stickers

##### Changed Constructors

- Added starref_program parameter in userFull

- Added starref_commission_permille, starref_peer, starref_amount parameters, changed type of stars from long to StarsAmount in starsTransaction

- Changed type of balance from long to StarsAmount in payments.starsStatus

- Changed type of balance from long to StarsAmount in updateStarsBalance

- Changed type of current_balance from long to StarsAmount, available_balance from long to StarsAmount, overall_revenue from long to StarsAmount in starsRevenueStatus

#### Schema

### Layer 194

- Bot subscription improvements »

- Search improvements »

#### Schema changes

##### Changed Methods

- Added groups_only, users_only parameters in messages.searchGlobal

- Removed invoice_slug parameter, changed type of charge_id from flags.2?string to string in payments.botCancelStarsSubscription

##### Changed Constructors

- Added subscription_until_date parameter in messageActionPaymentSentMe

- Added subscription_until_date parameter in messageActionPaymentSent

#### Schema

### Layer 193

This layer introduces the following new features, mainly related to Mini Apps 2.0:

- Prepared inline messages from mini apps »

- Setting a user's emoji status from a bot/mini app

- Mini app file downloads »

- Share stories from a mini app »

- Bot subscriptions »

- payments.exportInvoice can now be invoked over a business connection to generate subscription invoice links for business bots

- Fullscreen mini apps

- Added the fullscreen parameter to webViewResultUrl to allow opening apps in fullscreen mode by default (editable via botfather, can also be enabled by setting the fullscreen flag in the requestWebView methods)

- The mode parameter of main mini app links and direct mini app links now supports fullscreen mode, which forces setting the fullscreen flag in the requestWebView methods

- Added a web_app_request_fullscreen » method to request fullscreen mode in mini apps

- Gifts from bots, gift privacy settings and birthday-themed gifts »

- Customization for the mini app loading screen »

- Accelerometer tracking for mini apps »

- Gyroscope tracking for mini apps »

- Device orientation tracking for mini apps »

- Orientation lock for mini apps »

- Geolocation support for mini apps »

- Visibility tracking for mini apps »

- Add mini apps to the homescreen »

- Methods usable by mini apps to obtain the current content-defined » and system-defined » safe areas

- Allow customizing the vertical swipe behavior in mini apps »

- A secondary button for mini apps »

- Shine effect support for the main button of mini apps with a new has_shine_effect flag »

- Even more theming options for mini apps with a custom bottom bar color »

- Added a force_request parameter to the web_app_open_tg_link method »: if set and true, the client must ignore any locally cached information for the deep link (mainly used to refresh the cache information for stickerset links »).

- Additionally, now the method must not close the web app when invoked (regardless of the value of force_request).

The following new web events » were added:

- web_app_setup_swipe_behavior »

- web_app_set_bottom_bar_color »

- web_app_setup_secondary_button »

- web_app_share_to_story »

- web_app_request_fullscreen »

- web_app_exit_fullscreen »

- web_app_start_gyroscope »

- web_app_stop_gyroscope »

- web_app_start_device_orientation »

- web_app_stop_device_orientation »

- web_app_add_to_home_screen »

- web_app_check_home_screen »

- web_app_set_emoji_status »

- web_app_request_emoji_status_access »

- web_app_request_safe_area »

- web_app_request_content_safe_area »

- web_app_check_location »

- web_app_request_location »

- web_app_open_location_settings »

- web_app_request_file_download »

- web_app_send_prepared_message »

- web_app_toggle_orientation_lock »

The following new mini app events » were added:

- visibility_changed »

- secondary_button_pressed »

- fullscreen_changed »

- fullscreen_failed »

- accelerometer_started »

- accelerometer_failed »

- accelerometer_stopped »

- accelerometer_changed »

- gyroscope_started »

- gyroscope_failed »

- gyroscope_stopped »

- gyroscope_changed »

- device_orientation_started »

- device_orientation_failed »

- device_orientation_stopped »

- device_orientation_changed »

- home_screen_added »

- home_screen_failed »

- home_screen_checked »

- emoji_status_failed »

- emoji_status_set »

- emoji_status_access_requested »

- file_download_requested »

- prepared_message_failed »

- prepared_message_sent »

- safe_area_changed »

- content_safe_area_changed »

- location_requested »

- location_checked »

#### Schema changes

##### New Methods

- Added messages.savePreparedInlineMessage - Save a prepared inline message, to be shared by the user of the mini app using a web_app_send_prepared_message event

- Added messages.getPreparedInlineMessage - Obtain a prepared inline message generated by a mini app: invoked when handling web_app_send_prepared_message events

- Added bots.updateUserEmojiStatus - Change the emoji status of a user (invoked by bots, see here » for more info on the full flow)

- Added bots.toggleUserEmojiStatusPermission - Allow or prevent a bot from changing our emoji status »

- Added bots.checkDownloadFileParams - Check if a mini app can request the download of a specific file: called when handling web_app_request_file_download events »

- Added payments.botCancelStarsSubscription - Cancel a bot subscription

##### Changed Methods

- Added fullscreen parameter in messages.requestWebView

- Added fullscreen parameter in messages.requestSimpleWebView

- Added fullscreen parameter in messages.requestAppWebView

- Added fullscreen parameter in messages.requestMainWebView

##### New Constructors

- Added inputPrivacyKeyStarGiftsAutoSave - Whether received gifts will be automatically displayed on our profile

- Added privacyKeyStarGiftsAutoSave - Whether received gifts will be automatically displayed on our profile

- Added inputPrivacyValueAllowBots - Allow bots and mini apps

- Added inputPrivacyValueDisallowBots - Disallow bots and mini apps

- Added privacyValueAllowBots - Allow bots and mini apps

- Added privacyValueDisallowBots - Disallow bots and mini apps

- Added messages.botPreparedInlineMessage - Represents a prepared inline message saved by a bot, to be sent to the user via a web app »

- Added messages.preparedInlineMessage - Represents a prepared inline message received via a bot's mini app, that can be sent to some chats »

- Added botAppSettings - Mini app » settings

##### Changed Constructors

- Changed type of convert_stars from long to flags.4?long in messageActionStarGift

- Added bot_can_manage_emoji_status parameter in userFull

- Added app_settings parameter in botInfo

- Added subscription_period parameter in invoice

- Added fullscreen parameter in webViewResultUrl

- Added bot_canceled, title, photo, invoice_slug parameters in starsSubscription

- Added birthday parameter in starGift

#### Schema

### Layer 192

This layer introduces the following new features:

- Support for paid broadcasts for bots, through the new allow_paid_floodskip flag.

- Ads for bots

- Allow filtering out stories only sent by a certain peer when using stories.searchPosts

- Messages attached to gifts and other gift improvements

- Updates for sent scheduled messages (including videos sent from the conversion queue), thanks to the sent_messages flag of updateDeleteScheduledMessages

#### Schema changes

##### New Methods

- Added messages.viewSponsoredMessage - Mark a specific sponsored message » as read

- Added messages.clickSponsoredMessage - Informs the server that the user has interacted with a sponsored message in one of the ways listed here ».

- Added messages.reportSponsoredMessage - Report a sponsored message », see here » for more info on the full flow.

- Added messages.getSponsoredMessages - Get a list of sponsored messages for a peer, see here » for more info.

##### Changed Methods

- Added allow_paid_floodskip parameter in messages.sendMessage

- Added allow_paid_floodskip parameter in messages.sendMedia

- Added allow_paid_floodskip parameter in messages.forwardMessages

- Added allow_paid_floodskip parameter in messages.sendMultiMedia

- Added peer parameter, removed channel parameter in stats.getBroadcastRevenueStats

- Added peer parameter, removed channel parameter in stats.getBroadcastRevenueWithdrawalUrl

- Added peer parameter, removed channel parameter in stats.getBroadcastRevenueTransactions

- Added peer parameter in stories.searchPosts

##### Deleted Methods

- Removed channels.viewSponsoredMessage

- Removed channels.getSponsoredMessages

- Removed channels.clickSponsoredMessage

- Removed channels.reportSponsoredMessage

##### New Constructors

- Added starsTransactionPeerAPI - Describes a Telegram Star transaction used to pay for paid API usage, such as paid bot broadcasts.

##### Changed Constructors

- Added can_view_revenue parameter in userFull

- Added flags, sent_messages parameters in updateDeleteScheduledMessages

- Added message parameter in messageActionGiftPremium

- Added message parameter in inputStorePaymentPremiumGiftCode

- Added message parameter in messageActionGiftCode

- Added floodskip_number parameter in starsTransaction

- Added sold_out, first_sale_date, last_sale_date parameters in starGift

#### Schema

### Layer 189

This layer adds support for the following features:

- Automatic conversion of uploaded videos »

- Gifts »

- Clipboard button »

- Sponsored message improvements »

- Improvements to the reporting flow »

The following new config keys were added:

- stargifts_message_length_max »

- stargifts_blocked »

- stargifts_convert_period_max »

- video_ignore_alt_documents »

- sponsored_links_inapp_allow »

#### Schema changes

##### New Methods

- Added payments.getStarGifts - Get a list of available gifts, see here » for more info.

- Added payments.getUserStarGifts

- Added payments.saveStarGift - Display or remove a received gift » from our profile.

- Added payments.convertStarGift - Convert a received gift » into Telegram Stars: this will permanently destroy the gift, converting it into starGift.convert_stars Telegram Stars, added to the user's balance.

##### Changed Methods

- Changed type of messages.report from Bool to ReportResult

- Added option parameter, removed reason parameter in messages.report

- Added flags, media, fullscreen parameters in channels.clickSponsoredMessage

- Changed type of stories.report from Bool to ReportResult

- Added option parameter, removed reason parameter in stories.report

- Removed flags parameter in payments.sendStarsForm

##### New Constructors

- Added keyboardButtonCopy - Clipboard button: when clicked, the attached text must be copied to the clipboard.

- Added starGift - Represents a star gift, see here » for more info.

- Added payments.starGiftsNotModified - The list of available gifts » hasn't changed.

- Added payments.starGifts - Available gifts ».

- Added inputInvoiceStarGift - Used to buy a Telegram Star Gift, see here » for more info.

- Added payments.paymentFormStarGift - Represents a payment form for a gift, see here » for more info.

- Added messageActionStarGift - You received a gift, see here » for more info.

- Added userStarGift

- Added payments.userStarGifts

- Added messageReportOption - Report menu option

- Added reportResultChooseOption - The user must choose one of the following options, and then messages.report must be re-invoked, passing the option's option identifier to messages.report.option.

- Added reportResultAddComment - The user should enter an additional comment for the moderators, and then messages.report must be re-invoked, passing the comment to messages.report.message.

- Added reportResultReported - The report was sent successfully, no further actions are required.

##### Changed Constructors

- Added video_processing_pending parameter in message

- Added stargifts_count parameter in userFull

- Added alt_documents parameter, removed alt_document parameter in messageMediaDocument

- Added video_codec parameter in documentAttributeVideo

- Added stargift parameter in starsTransaction

#### PUSH notification changes

##### New PUSH notifications

- Added MESSAGE_STARGIFT - {1} sent you a Gift worth {2} Stars

#### Schema

### Layer 187

This layer adds support for the following features:

- Star giveaways »

- Paid reaction privacy settings »

- Paid media for bots »

- Improvements to star subscriptions »

#### Schema changes

##### New Methods

- Added payments.getStarsGiveawayOptions - Fetch a list of star giveaway options ».

- Added messages.getPaidReactionPrivacy - Fetches an updatePaidReactionPrivacy update with the current default paid reaction privacy, see here » for more info.

##### Changed Methods

- Changed type of private from flags.0?true to flags.0?Bool in messages.sendPaidReaction

##### New Constructors

- Added updateBotPurchasedPaidMedia - Bots only: a user has purchased a paid media.

- Added channelAdminLogEventActionParticipantSubExtend - A paid subscriber has extended their Telegram Star subscription ».

- Added inputStorePaymentStarsGiveaway - Used to pay for a star giveaway, see here » for more info.

- Added messageActionPrizeStars - You won some Telegram Stars in a Telegram Star giveaway ».

- Added updatePaidReactionPrivacy - Contains the current default paid reaction privacy, see here » for more info.

- Added starsGiveawayOption - Contains info about a Telegram Star giveaway option.

- Added starsGiveawayWinnersOption - Allowed options for the number of giveaway winners.

- Added prepaidStarsGiveaway - Contains info about a prepaid Telegram Star giveaway ».

##### Changed Constructors

- Added sub_extend parameter in channelAdminLogEventsFilter

- Added stars parameter, changed type of months from int to flags.4?int in messageMediaGiveaway

- Added flags, stars parameters in messageActionGiveawayLaunch

- Added stars_prize parameter, changed type of gift_code_slug from flags.0?string to flags.3?string, activated_count from int to flags.2?int in payments.giveawayInfoResults

- Added stars parameter in boost

- Added flags, stars parameters in messageActionGiveawayResults

- Added stars parameter, changed type of months from int to flags.4?int in messageMediaGiveawayResults

- Added flags, withdrawal_enabled parameters in broadcastRevenueBalances

- Added giveaway_post_id parameter in starsTransaction

- Added flags, payload parameters in inputMediaPaidMedia

#### PUSH notification changes

##### New PUSH notifications

- Added CHANNEL_MESSAGE_GIVEAWAY_STARS - {1} posted a giveaway of {3} stars {2}

- Added CHAT_MESSAGE_GIVEAWAY_STARS - {1} sent a giveaway of {4} stars {3} to the group {2}

- Added MESSAGE_GIVEAWAY_STARS - {1} sent you a giveaway of {3} stars {2}

#### Schema

### Layer 186

This layer adds support for the following features:

- Telegram Star subscriptions »

- Paid reactions »

- Super channels »

- You can now send channel messages that look exactly like group messages, with full information about the sender (and the same UI used for messages in groups): to toggle this feature, invoke channels.toggleSignatures with signatures_enabled and profiles_enabled set.

- Enabling this mode will allow admins to post messages to the channel as any of the profiles they control (including other channels, and the channel itself for anonymous messages like the default mode) with the send_as flag of messages.sendMessage and other message sending methods.

- The new channel.signature_profiles flag is a valid min field.

- Media in sponsored messages

- Privacy policies for bots through the botInfo.privacy_policy_url parameter.

The following new suggestions were added:

- STARS_SUBSCRIPTION_LOW_BALANCE »

The following new config keys were added:

- stars_subscription_amount_max »

- stars_usd_sell_rate_x1000 »

- stars_usd_withdraw_rate_x1000 »

- stars_paid_reaction_amount_max »

The following new deep links were added:

- Stars topup link »

