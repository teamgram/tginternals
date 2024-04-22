# Stickers

Telegram clients support displaying static and animated stickers.

### Displaying stickers

Stickers can be contained in document constructors attached to messages, and always have an attribute of type documentAttributeSticker.

The documentAttributeSticker attribute contains information about the associated stickerset, the emoji that represents the sticker, and more.

There are multiple available sticker types:

- Static stickers »

- Animated stickers »

- Video stickers »

Like all files, stickers have a set of previews that should be handled as described here ».

Stickers are organized in stickersets », and are also used in the following contexts:

- Dice »

- Animated emojis »

- Custom emojis »

- Reactions »

- Mask stickers »

#### Static stickers

Static stickers are WebP images with the following specs:

- For stickers, either width or height must be equal to 512 pixels.

- For custom emojis, the resolution must be equal to 100x100 pixels.

- Transparency is supported.

They're identified by mime_type field of the associated document, always equal to image/webp.

See here » for tips on how to create the perfect static sticker, and here » for info on how to upload it using the API.

#### Animated stickers

Animated stickers are Lottie vector animations ».

Telegram uses a special .tgs file format for lottie animations, which consists in a gzipped bodymovin JSON file, playable using the rlottie library.

Lottie animation specs:

- The canvas size must be 512х512 pixels.

- Objects must not leave the canvas.

- Animation length must not exceed 3 seconds.

- All animations must be looped.

- All animations must run at 60 Frames Per Second.

They're identified by mime_type field of the associated document, always equal to application/x-tgsticker.

See here » for tips on how to create the perfect animated sticker, and here » for info on how to upload it using the API.

#### Video stickers

Video stickers are VP9 videos with the following specs:

- The video must be encoded using VP9, in a WebM container.

- The WebM container must have no audio stream.

- For stickers, either width or height must be equal to 512 pixels.

- For custom emojis, the resolution must be equal to 100x100 pixels.

- Maximum duration: 3 seconds.

- Frame rate: up to 30 FPS.

- Transparency is supported.

- The video should be looped for optimal user experience.

They're identified by mime_type field of the associated document, always equal to video/webm.

See here » for tips on how to create the perfect video sticker, and here » for info on how to upload it using the API.

### Stickersets

Stickers are grouped together in so-called sticker packs: however, in the API they're referred to as "sticker sets", and the name "sticker pack" is reserved for something else, read on for more info.

Use messages.getStickerSet to fetch information about the stickerset, providing the following parameters:

- stickerset - One of the following constructors:

- inputStickerSetID - For stickersets contained in received messages

- inputStickerSetShortName - For stickersets contained in sticker deep links »

- inputStickerSetAnimatedEmoji - For animated emoji » stickers.

- inputStickerSetAnimatedEmojiAnimations - For animated emoji reaction » stickers.

- inputStickerSetDice - For dice » stickersets.

- inputStickerSetPremiumGifts - For premium gift animation » stickers.

- inputStickerSetEmojiGenericAnimations - For generic emoji reaction animations.

- inputStickerSetEmojiDefaultStatuses - Standard emoji status stickerset.

- hash - Initially 0, afterwards should contain the hash field from the returned stickerSet.

The method will return a messages.stickerSetNotModified if a non-zero hash is provided and the stickerset wasn't modified since the last time we fetched it.
Otherwise, a messages.stickerSet will be returned, containing:

- A stickerSet constructor with info about the stickerset

- A vector of document constructors, containing all the stickers.

- Note that even if we provided an old hash and just a few stickers were modified/reordered, all stickers will be returned anyway.

- A vector of stickerPack constructors, containing all the stickers IDs in the stickerpack, grouped by emoji.

- The main emoji to use when previewing stickers in the chat list is present in the alt field of the document.

- This field is actually used to allow associating more than one emoji to a sticker: this means that the same document ID may be present in multiple stickerPacks.

### Stickerset previews

Certain parts of the API may return partial StickerSetCovered constructors instead of full document constructors for every sticker in the set:

- stickerSetCovered - Contains generic info about a stickerset and one preview sticker: use messages.getStickerSet to fetch all the stickers in the stickerset.

- stickerSetMultiCovered - Contains generic info about a stickerset and multiple preview stickers: use messages.getStickerSet to fetch all the stickers in the stickerset.

- stickerSetFullCovered - Contains generic info about a stickerset and all stickers in the set (not just a preview): currently only used for custom emoji stickersets, to avoid a further call to messages.getStickerSet.

Also, like all files, sticker documents have a set of previews that should be handled as described here ».

### Installing stickersets

A stickerset can be installed using messages.installStickerSet, archived=false, with possible return values:

- messages.stickerSetInstallResultSuccess - The stickerset was successfully installed

- messages.stickerSetInstallResultArchive - The stickerset was successfully installed, displacing some older unused stickersets specified in the sets field by archiving them.

Use messages.uninstallStickerSet or messages.toggleStickerSets with the uninstall flag to uninstall one or more stickersets.

An updateNewStickerSet update will be emitted to the other logged-in sessions when installing stickersets.

An updateStickerSets update will be emitted to the other logged-in sessions when uninstalling or archiving stickersets.
This update should trigger a call to the following methods:

- If masks is set, call messages.getMaskStickers.

- If emoji is set, call messages.getEmojiStickers.

- Otherwise, call messages.getAllStickers and messages.getArchivedStickers.

Use messages.reorderStickerSets to reorder installed stickersets by the stickerSet ID: notice that normal, mask and custom emoji stickersets are ordered independently, use the appropriate flags to sort the correct type of stickerset.

An updateStickerSetsOrder update will be emitted to the other logged-in sessions when reordering stickersets.
This update should trigger a call to messages.getAllStickers, messages.getArchivedStickers, messages.getEmojiStickers.

Use messages.getAllStickers to fetch all installed and non-archived stickersets.
Use messages.getEmojiStickers to fetch all installed and non-archived custom emoji stickersets.

### Creating stickersets

Bots and users can create stickersets by using the following methods.
Users can also create stickersets by interacting with the official @stickers bot.

Note that unofficial bots must append a "_by_<bot_username>" prefix to the stickerset short name when creating stickersets.
Also note that users can't directly modify stickersets created using stickers.createStickerSet, and must use the @stickers bot, instead: only the sticker creation+shortname methods are available directly to users to allow importing stickers using the stickers SDK.

Use messages.uploadMedia to upload stickers and thumbnails, if you don't already have access to a previously uploaded document.

Use stickers.checkShortName to check if a given short name is available, and stickers.suggestShortName to let the server suggest a short name, given the stickerset title.

Use stickers.createStickerSet to create normal, animated, video or mask stickersets.
Custom emoji stickersets can only be created using the @stickers bot for now.

Use stickers.addStickerToSet to add stickers to the stickerset.
Use stickers.setStickerSetThumb to edit the stickerset thumbnail after creation.
Use stickers.removeStickerFromSet to remove stickers from a stickerset, and stickers.changeStickerPosition to move stickers in a stickerset (simply providing the sticker document is enough).

### Searching stickersets

You can use messages.searchStickerSets and messages.searchEmojiStickerSets to search globally available normal stickersets and custom emoji stickersets » by name: note that this method returns a set of stickerset previews ».

### Featured stickersets

Telegram showcases a set of featured stickersets: they can be fetched using messages.getFeaturedStickers or messages.getFeaturedEmojiStickers, for custom emojis.

Clients should preload featured stickers on startup according to the value of the preload_featured_stickers configuration parameter.

The method also returns a set of unread stickerSet IDs in the unread field: use messages.readFeaturedStickers to mark them as read: note that this will only affect the unread field, all stickersets will still be returned, unless you also generate a hash.
This method will also emit an updateReadFeaturedStickers or updateReadFeaturedEmojiStickers update on all other logged-in sessions.

messages.getOldFeaturedStickers can be used to fetch an extended list with even more featured stickersets, that were previously featured in the short list returned by messages.getFeaturedStickers.

### Favorite stickersets

A stickerset can be faved or unfaved using messages.faveSticker.

Favorited stickers can be fetched using messages.getFavedStickers: note that this method returns a set of stickerset previews ».

Users can fave only a certain number of stickersets, as specified by the following configuration parameters:

- Premium users can fave a total of stickers_faved_limit_premium stickersets.

- Non-Premium users can fave a total of stickers_faved_limit_default stickersets.

An updateFavedStickers update will be emitted to the other logged-in sessions when faving or unfaving stickersets.
This update should trigger a call to messages.getFavedStickers.

### Archived stickersets

One or more stickersets can be archived (or unarchived) using messages.installStickerSet with archived=true|false, or messages.toggleStickerSets with either the archive or unarchive flag.

An unused stickerset may also be automatically archived when installing new stickersets.

Archived stickers are not returned by messages.getAllStickers and can only be fetched using messages.getArchivedStickers: note that this method returns a set of stickerset previews ».

An updateStickerSets update will be emitted to the other logged-in sessions when archiving or unarchiving stickersets.
This update should trigger a call to messages.getArchivedStickers.

### Recent stickers

After using a sticker in a message, clients should invoke messages.saveRecentSticker (normal and mask stickers only, mask stickers should set the attached flag).

A sticker can be then removed from the recent stickers list using messages.saveRecentSticker with unsave=true; the entire list can be cleared using messages.clearRecentStickers.

Use messages.getRecentStickers to fetch the recent stickers list.

Users can add only a certain number of recent stickers, according to the value of the stickers_recent_limit configuration parameter.

An updateRecentStickers update will be emitted to the other logged-in sessions when modifying the recent stickerset list.
This update should trigger a call to messages.getRecentStickers.

### Recent stickersets

The update_stickersets_order flag should be set when manually choosing and using stickers, masks and custom emojis from a specific stickerset in the stickerset selection bar (not through suggested or recent stickersets UI views).
Note that for custom emojis, the flag should only be set when manually choosing custom emojis from a single custom emoji stickerset (not multiple custom emoji stickersets).

Setting this flag will trigger an updateMoveStickerSetToTop update (instead of the usual updateStickerSetsOrder/updateStickerSets updates), indicating that the installed stickerset list was reordered and the specified stickerset was moved to the top.

Note that the API also offers a separate list of recent stickers (not stickersets), see here » for more info.

### Sticker suggestions

Clients should show a popup with a list of suggested stickers and custom emojis when the user enters an emoji in the text bar.

If the stickers_emoji_suggest_only_api app configuration parameter is set to true, clients must invoke messages.getStickers/messages.searchCustomEmoji to fetch a list of suggested stickers/custom emojis for the emoji.
The stickers_emoji_cache_time appConfig parameter specifies the validity period of the local cache of messages.getStickers/messages.searchCustomEmoji, also relevant when generating the pagination hash when invoking the method.

Otherwise, the following local logic should be used.

- Construct two lists of recently used stickers, matching the emoji:

- List a) Contains all non-Premium stickers.

- List b) Contains all Premium stickers.

- The final suggested sticker list c is composed as follows:

- If the user doesn't have a Premium subscription: all stickers from a, followed by stickers_premium_by_emoji_num stickers from b.

- If the user has a Premium subscription: stickers_normal_by_emoji_per_premium_num stickers from a, followed by 1 sticker from b, and so on until both lists are empty.

### Attached stickers

Stickers of all kinds can be attached to photos and videos.
First, overlay the sticker on top of the media file locally (properly handling eventual default mask coordinates), and upload the modified media file.
Then, when sending the media file using messages.sendMedia, indicate the stickers that were overlaid in the stickers field of inputMediaUploadedPhoto or inputMediaUploadedDocument.

Sent stickered photos will have the has_stickers flag set.
Sent stickered video documents will have a documentAttributeHasStickers attribute.

When receiving such a media file, clients should call messages.getAttachedStickers, passing the media: the method will return a set of stickerset previews », with info about the stickersets (not stickers) used in the media.

#### Mask stickers

Mask stickers are a special kind of static stickers that are meant to be overlaid on top of photos and attached to media, as specified here ».

Mask stickers can optionally have associated coordinates, contained in the maskCoords constructor.

The n position indicates where the mask should be placed:

- 0 => Relative to the forehead

- 1 => Relative to the eyes

- 2 => Relative to the mouth

- 3 => Relative to the chin

The x, y and zoom parameters further refine the position relative to the chosen facial feature.

Note that these coordinates are only used to provide a default position when attaching stickers to media, by locally running facial recognition software and placing the mask sticker at the appropriate coordinates relative to the chosen facial feature.
The final sticker position can be modified by the user before generating a new photo/video with the sticker baked-in.
The final coordinates will not be sent along with the attached media, as they are only used as a suggested default position when placing the sticker.

The default coordinates are chosen by the stickerset creator when uploading the sticker.

