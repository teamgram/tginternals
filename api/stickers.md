# Stickers

Telegram clients support displaying static and animated stickers.

### Displaying stickers

```
document#8fd4c4d8 flags:# id:long access_hash:long file_reference:bytes date:int mime_type:string size:long thumbs:flags.0?Vector<PhotoSize> video_thumbs:flags.1?Vector<VideoSize> dc_id:int attributes:Vector<DocumentAttribute> = Document;

documentAttributeSticker#6319d612 flags:# mask:flags.1?true alt:string stickerset:InputStickerSet mask_coords:flags.0?MaskCoords = DocumentAttribute;

inputStickerSetEmpty#ffb62b95 = InputStickerSet;
inputStickerSetID#9de7a269 id:long access_hash:long = InputStickerSet;
inputStickerSetShortName#861cc8a0 short_name:string = InputStickerSet;
inputStickerSetAnimatedEmoji#28703c8 = InputStickerSet;
inputStickerSetDice#e67f520e emoticon:string = InputStickerSet;
inputStickerSetAnimatedEmojiAnimations#cde3739 = InputStickerSet;
inputStickerSetPremiumGifts#c88b3b02 = InputStickerSet;
inputStickerSetEmojiGenericAnimations#4c4d4ce = InputStickerSet;
inputStickerSetEmojiDefaultStatuses#29d0f5ee = InputStickerSet;
inputStickerSetEmojiDefaultTopicIcons#44c1f8e9 = InputStickerSet;
inputStickerSetEmojiChannelDefaultStatuses#49748553 = InputStickerSet;
```

Stickers can be contained in document constructors attached to messages, and always have an attribute of type documentAttributeSticker.

The documentAttributeSticker attribute contains information about the associated stickerset, the emoji that represents the sticker, and more.

There are multiple available sticker types:

- Static stickers »

- Animated stickers »

- Video stickers »

Like all files, stickers have a set of previews that should be handled as described here ».

Stickers are organized in stickersets », and are also used in the following contexts:

- Dice »

- Animated emojis »

- Custom emojis »

- Reactions »

- Mask stickers »

A single stickerset can contain a mix of static, animated and video stickers.

#### Static stickers

Static stickers are WebP images with the following specs:

- For stickers, either width or height must be equal to 512 pixels.

- For custom emojis, the resolution must be equal to 100x100 pixels.

- Transparency is supported.

They're identified by mime_type field of the associated document, always equal to image/webp.

See here » for tips on how to create the perfect static sticker, and here » for info on how to upload it using the API.

#### Animated stickers

Animated stickers are Lottie vector animations ».

Telegram uses a special .tgs file format for lottie animations, which consists in a gzipped bodymovin JSON file, playable using the rlottie library.

Lottie animation specs:

- The canvas size must be 512х512 pixels.

- Objects must not leave the canvas.

- Animation length must not exceed 3 seconds.

- All animations must be looped.

- All animations must run at 60 Frames Per Second.

They're identified by mime_type field of the associated document, always equal to application/x-tgsticker.

See here » for tips on how to create the perfect animated sticker, and here » for info on how to upload it using the API.

##### Premium animated sticker effects

```
document#8fd4c4d8 flags:# id:long access_hash:long file_reference:bytes date:int mime_type:string size:long thumbs:flags.0?Vector<PhotoSize> video_thumbs:flags.1?Vector<VideoSize> dc_id:int attributes:Vector<DocumentAttribute> = Document;

videoSize#de33b094 flags:# type:string w:int h:int size:int video_start_ts:flags.0?double = VideoSize;

inputDocumentFileLocation#bad07584 id:long access_hash:long file_reference:bytes thumb_size:string = InputFileLocation;
```

Some animated stickers also have an attached animated effect (as another Lottie animation), that should be played once the sticker is inside the viewport.

This effect is larger than the sticker itself, and should be located under the main sticker animation, but also over any other nearby UI element.

It should be played the first time the sticker scrolls into view; it should be played again if the chat is closed and then opened again.

Premium stickers may only be sent by users with a Premium subscription, and the animated effect should be played by all users, including those without a Premium subscription.

A premium sticker is identified by the presence of a videoSize of type=f in the sticker's main document.
The TGS file of the animated effect (different from the TGS file of the sticker itself) may be fetched by using inputDocumentFileLocation with thumb_size=f, as specified here ».

Note that animated message effects » can also re-use the animated effect of a premium sticker.

Also, premium animated stickers may be sent with an extra animated message effect », in which case both the effect of the sticker and the additional effect should be played simultaneously.

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

See here » for tips on how to create the perfect video sticker, and here » for info on how to upload it using the API.

### Stickersets

```
inputStickerSetID#9de7a269 id:long access_hash:long = InputStickerSet;
inputStickerSetShortName#861cc8a0 short_name:string = InputStickerSet;
inputStickerSetAnimatedEmoji#28703c8 = InputStickerSet;
inputStickerSetDice#e67f520e emoticon:string = InputStickerSet;
inputStickerSetAnimatedEmojiAnimations#cde3739 = InputStickerSet;
inputStickerSetPremiumGifts#c88b3b02 = InputStickerSet;
inputStickerSetEmojiGenericAnimations#4c4d4ce = InputStickerSet;
inputStickerSetEmojiDefaultStatuses#29d0f5ee = InputStickerSet;
inputStickerSetEmojiDefaultTopicIcons#44c1f8e9 = InputStickerSet;
inputStickerSetEmojiChannelDefaultStatuses#49748553 = InputStickerSet;

messages.stickerSet#6e153f16 set:StickerSet packs:Vector<StickerPack> keywords:Vector<StickerKeyword> documents:Vector<Document> = messages.StickerSet;
messages.stickerSetNotModified#d3f924eb = messages.StickerSet;

stickerSet#2dd14edc flags:# archived:flags.1?true official:flags.2?true masks:flags.3?true emojis:flags.7?true text_color:flags.9?true channel_emoji_status:flags.10?true creator:flags.11?true installed_date:flags.0?int id:long access_hash:long title:string short_name:string thumbs:flags.4?Vector<PhotoSize> thumb_dc_id:flags.4?int thumb_version:flags.4?int thumb_document_id:flags.8?long count:int hash:int = StickerSet;

stickerPack#12b299d4 emoticon:string documents:Vector<long> = StickerPack;

---functions---

messages.getStickerSet#c8a0ec74 stickerset:InputStickerSet hash:int = messages.StickerSet;
```

Stickers are grouped together in so-called sticker packs: however, in the API they're referred to as "sticker sets", and the name "sticker pack" is reserved for something else, read on for more info.

Use messages.getStickerSet to fetch information about the stickerset, providing the following parameters:

- stickerset - One of the constructors specified here », choose the correct one, according to the stickerset that is being fetched.

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

```
stickerSetCovered#6410a5d2 set:StickerSet cover:Document = StickerSetCovered;
stickerSetMultiCovered#3407e51b set:StickerSet covers:Vector<Document> = StickerSetCovered;
stickerSetFullCovered#40d13c0e set:StickerSet packs:Vector<StickerPack> keywords:Vector<StickerKeyword> documents:Vector<Document> = StickerSetCovered;
```

Certain parts of the API may return partial StickerSetCovered constructors instead of full document constructors for every sticker in the set:

- stickerSetCovered - Contains generic info about a stickerset and one preview sticker: use messages.getStickerSet to fetch all the stickers in the stickerset.

- stickerSetMultiCovered - Contains generic info about a stickerset and multiple preview stickers: use messages.getStickerSet to fetch all the stickers in the stickerset.

- stickerSetFullCovered - Contains generic info about a stickerset and all stickers in the set (not just a preview): currently only used for custom emoji stickersets, to avoid a further call to messages.getStickerSet.

Also, like all files, sticker documents have a set of previews that should be handled as described here ».

### Installing stickersets

```
inputStickerSetID#9de7a269 id:long access_hash:long = InputStickerSet;
inputStickerSetShortName#861cc8a0 short_name:string = InputStickerSet;
inputStickerSetAnimatedEmoji#28703c8 = InputStickerSet;
inputStickerSetDice#e67f520e emoticon:string = InputStickerSet;
inputStickerSetAnimatedEmojiAnimations#cde3739 = InputStickerSet;
inputStickerSetPremiumGifts#c88b3b02 = InputStickerSet;
inputStickerSetEmojiGenericAnimations#4c4d4ce = InputStickerSet;
inputStickerSetEmojiDefaultStatuses#29d0f5ee = InputStickerSet;
inputStickerSetEmojiDefaultTopicIcons#44c1f8e9 = InputStickerSet;
inputStickerSetEmojiChannelDefaultStatuses#49748553 = InputStickerSet;

messages.stickerSetInstallResultSuccess#38641628 = messages.StickerSetInstallResult;
messages.stickerSetInstallResultArchive#35e410a8 sets:Vector<StickerSetCovered> = messages.StickerSetInstallResult;

messages.allStickersNotModified#e86602c3 = messages.AllStickers;
messages.allStickers#cdbbcebb hash:long sets:Vector<StickerSet> = messages.AllStickers;

updateNewStickerSet#688a30aa stickerset:messages.StickerSet = Update;
updateStickerSetsOrder#bb2d201 flags:# masks:flags.0?true emojis:flags.1?true order:Vector<long> = Update;
updateStickerSets#31c24808 flags:# masks:flags.0?true emojis:flags.1?true = Update;

---functions---

messages.installStickerSet#c78fe460 stickerset:InputStickerSet archived:Bool = messages.StickerSetInstallResult;
messages.uninstallStickerSet#f96e55de stickerset:InputStickerSet = Bool;
messages.toggleStickerSets#b5052fea flags:# uninstall:flags.0?true archive:flags.1?true unarchive:flags.2?true stickersets:Vector<InputStickerSet> = Bool;
messages.reorderStickerSets#78337739 flags:# masks:flags.0?true emojis:flags.1?true order:Vector<long> = Bool;
messages.getAllStickers#b8a0a1a8 hash:long = messages.AllStickers;
messages.getMaskStickers#640f82b8 hash:long = messages.AllStickers;
messages.getEmojiStickers#fbfca18f hash:long = messages.AllStickers;
```

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

```
inputStickerSetItem#32da9e9c flags:# document:InputDocument emoji:string mask_coords:flags.0?MaskCoords keywords:flags.1?string = InputStickerSetItem;

messages.stickerSet#6e153f16 set:StickerSet packs:Vector<StickerPack> keywords:Vector<StickerKeyword> documents:Vector<Document> = messages.StickerSet;
messages.stickerSetNotModified#d3f924eb = messages.StickerSet;

messages.myStickers#faff629d count:int sets:Vector<StickerSetCovered> = messages.MyStickers;

stickers.suggestedShortName#85fea03f short_name:string = stickers.SuggestedShortName;

---functions---

messages.uploadMedia#14967978 flags:# business_connection_id:flags.0?string peer:InputPeer media:InputMedia = MessageMedia;

stickers.checkShortName#284b3639 short_name:string = Bool;
stickers.suggestShortName#4dafc503 title:string = stickers.SuggestedShortName;

stickers.createStickerSet#9021ab67 flags:# masks:flags.0?true emojis:flags.5?true text_color:flags.6?true user_id:InputUser title:string short_name:string thumb:flags.2?InputDocument stickers:Vector<InputStickerSetItem> software:flags.3?string = messages.StickerSet;

messages.getMyStickers#d0b5e1fc offset_id:long limit:int = messages.MyStickers;

stickers.addStickerToSet#8653febe stickerset:InputStickerSet sticker:InputStickerSetItem = messages.StickerSet;
stickers.replaceSticker#4696459a sticker:InputDocument new_sticker:InputStickerSetItem = messages.StickerSet;
stickers.removeStickerFromSet#f7760f51 sticker:InputDocument = messages.StickerSet;
stickers.changeStickerPosition#ffb6d4ca sticker:InputDocument position:int = messages.StickerSet;
stickers.setStickerSetThumb#a76a5392 flags:# stickerset:InputStickerSet thumb:flags.0?InputDocument thumb_document_id:flags.1?long = messages.StickerSet;
```

Bots and users can create stickersets by using the following methods.
The @stickers bot which could be previously used to edit stickers is now deprecated, the in-app editor (invoking the following methods) should now be used, instead.

Note that unofficial bots must append a "_by_<bot_username>" prefix to the stickerset short name when creating stickersets.
Users and bots can directly modify stickersets created using stickers.createStickerSet and @stickers: stickersets owned by the current user/bot will have the creator flag set.

Use messages.getMyStickers to fetch the stickersets created by the current account.

Use messages.uploadMedia to upload stickers and thumbnails, if you don't already have access to a previously uploaded document.

Use stickers.checkShortName to check if a given short name is available, and stickers.suggestShortName to let the server suggest a short name, given the stickerset title.

Use stickers.createStickerSet to create normal, mask and custom emoji stickersets, also when importing stickers using the stickers SDK.

Use stickers.addStickerToSet to add stickers to the stickerset.
Use stickers.replaceSticker to replace a sticker in a stickerset (no need to pass the actual stickerset ID here).
Use stickers.setStickerSetThumb to edit the stickerset thumbnail after creation.
Use stickers.removeStickerFromSet to remove stickers from a stickerset, and stickers.changeStickerPosition to move stickers in a stickerset (simply providing the sticker document is enough).

### Searching stickersets

```
messages.foundStickerSetsNotModified#d54b65d = messages.FoundStickerSets;
messages.foundStickerSets#8af09dd2 hash:long sets:Vector<StickerSetCovered> = messages.FoundStickerSets;

---functions---

messages.searchStickerSets#35705b8a flags:# exclude_featured:flags.0?true q:string hash:long = messages.FoundStickerSets;

messages.searchEmojiStickerSets#92b4494c flags:# exclude_featured:flags.0?true q:string hash:long = messages.FoundStickerSets;
```

You can use messages.searchStickerSets and messages.searchEmojiStickerSets to search globally available normal stickersets and custom emoji stickersets » by name: note that this method returns a set of stickerset previews ».

### Searching stickers

```
messages.foundStickersNotModified#6010c534 flags:# next_offset:flags.0?int = messages.FoundStickers;
messages.foundStickers#82c9e290 flags:# next_offset:flags.0?int hash:long stickers:Vector<Document> = messages.FoundStickers;

---functions---

messages.searchStickers#29b1c66a flags:# emojis:flags.0?true q:string emoticon:string lang_code:Vector<string> offset:int limit:int hash:long = messages.FoundStickers;
```

You can use messages.searchStickers to search globally available normal and custom emoji stickers » using keywords (q) in multiple languages (which can be provided in lang_code) and/or a list of space-separated emojis (emoticon).

Thanks to a server-side custom AI model, this method supports complex searches with multiple keywords.

### Featured stickersets

```
messages.featuredStickersNotModified#c6dc0c66 count:int = messages.FeaturedStickers;
messages.featuredStickers#be382906 flags:# premium:flags.0?true hash:long count:int sets:Vector<StickerSetCovered> unread:Vector<long> = messages.FeaturedStickers;

updateReadFeaturedStickers#571d2742 = Update;
updateReadFeaturedEmojiStickers#fb4c496c = Update;

---functions---

messages.getFeaturedStickers#64780b14 hash:long = messages.FeaturedStickers;
messages.readFeaturedStickers#5b118126 id:Vector<long> = Bool;

messages.getOldFeaturedStickers#7ed094a1 offset:int limit:int hash:long = messages.FeaturedStickers;

messages.getFeaturedEmojiStickers#ecf6736 hash:long = messages.FeaturedStickers;
```

Telegram showcases a set of featured stickersets: they can be fetched using messages.getFeaturedStickers or messages.getFeaturedEmojiStickers, for custom emojis.

Clients should preload featured stickers on startup according to the value of the preload_featured_stickers configuration parameter.

The method also returns a set of unread stickerSet IDs in the unread field: use messages.readFeaturedStickers to mark them as read: note that this will only affect the unread field, all stickersets will still be returned, unless you also generate a hash.
This method will also emit an updateReadFeaturedStickers or updateReadFeaturedEmojiStickers update on all other logged-in sessions.

messages.getOldFeaturedStickers can be used to fetch an extended list with even more featured stickersets, that were previously featured in the short list returned by messages.getFeaturedStickers.

### Favorite stickersets

```
messages.favedStickersNotModified#9e8fa6d3 = messages.FavedStickers;
messages.favedStickers#2cb51097 hash:long packs:Vector<StickerPack> stickers:Vector<Document> = messages.FavedStickers;

updateFavedStickers#e511996d = Update;

---functions---

messages.faveSticker#b9ffc55b id:InputDocument unfave:Bool = Bool;
messages.getFavedStickers#4f1aaa9 hash:long = messages.FavedStickers;
```

A stickerset can be faved or unfaved using messages.faveSticker.

Favorited stickers can be fetched using messages.getFavedStickers: note that this method returns a set of stickerset previews ».

Users can fave only a certain number of stickersets, as specified by the following configuration parameters:

- Premium users can fave a total of stickers_faved_limit_premium stickersets.

- Non-Premium users can fave a total of stickers_faved_limit_default stickersets.

An updateFavedStickers update will be emitted to the other logged-in sessions when faving or unfaving stickersets.
This update should trigger a call to messages.getFavedStickers.

### Archived stickersets

```
messages.archivedStickers#4fcba9c8 count:int sets:Vector<StickerSetCovered> = messages.ArchivedStickers;

updateStickerSets#31c24808 flags:# masks:flags.0?true emojis:flags.1?true = Update;

---functions---

messages.installStickerSet#c78fe460 stickerset:InputStickerSet archived:Bool = messages.StickerSetInstallResult;
messages.toggleStickerSets#b5052fea flags:# uninstall:flags.0?true archive:flags.1?true unarchive:flags.2?true stickersets:Vector<InputStickerSet> = Bool;

messages.getArchivedStickers#57f17692 flags:# masks:flags.0?true emojis:flags.1?true offset_id:long limit:int = messages.ArchivedStickers;
```

One or more stickersets can be archived (or unarchived) using messages.installStickerSet with archived=true|false, or messages.toggleStickerSets with either the archive or unarchive flag.

An unused stickerset may also be automatically archived when installing new stickersets.

Archived stickers are not returned by messages.getAllStickers and can only be fetched using messages.getArchivedStickers: note that this method returns a set of stickerset previews ».

An updateStickerSets update will be emitted to the other logged-in sessions when archiving or unarchiving stickersets.
This update should trigger a call to messages.getArchivedStickers.

### Recent stickers

```
messages.recentStickersNotModified#b17f890 = messages.RecentStickers;
messages.recentStickers#88d37c56 hash:long packs:Vector<StickerPack> stickers:Vector<Document> dates:Vector<int> = messages.RecentStickers;

updateRecentStickers#9a422c20 = Update;

---functions---

messages.saveRecentSticker#392718f8 flags:# attached:flags.0?true id:InputDocument unsave:Bool = Bool;
messages.getRecentStickers#9da9403b flags:# attached:flags.0?true hash:long = messages.RecentStickers;
messages.clearRecentStickers#8999602d flags:# attached:flags.0?true = Bool;
```

After using a sticker in a message, clients should invoke messages.saveRecentSticker (normal and mask stickers only, mask stickers should set the attached flag).

A sticker can be then removed from the recent stickers list using messages.saveRecentSticker with unsave=true; the entire list can be cleared using messages.clearRecentStickers.

Use messages.getRecentStickers to fetch the recent stickers list.

Users can add only a certain number of recent stickers, according to the value of the stickers_recent_limit configuration parameter.

An updateRecentStickers update will be emitted to the other logged-in sessions when modifying the recent stickerset list.
This update should trigger a call to messages.getRecentStickers.

### Recent stickersets

```
updateMoveStickerSetToTop#86fccf85 flags:# masks:flags.0?true emojis:flags.1?true stickerset:long = Update;

---functions---

messages.sendMessage#fe05dc9a flags:# no_webpage:flags.1?true silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true allow_paid_floodskip:flags.19?true peer:InputPeer reply_to:flags.0?InputReplyTo message:string random_id:long reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.10?int send_as:flags.13?InputPeer quick_reply_shortcut:flags.17?InputQuickReplyShortcut effect:flags.18?long allow_paid_stars:flags.21?long suggested_post:flags.22?SuggestedPost = Updates;
messages.sendMedia#ac55d9c1 flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true allow_paid_floodskip:flags.19?true peer:InputPeer reply_to:flags.0?InputReplyTo media:InputMedia message:string random_id:long reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.10?int send_as:flags.13?InputPeer quick_reply_shortcut:flags.17?InputQuickReplyShortcut effect:flags.18?long allow_paid_stars:flags.21?long suggested_post:flags.22?SuggestedPost = Updates;
messages.sendMultiMedia#1bf89d74 flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true allow_paid_floodskip:flags.19?true peer:InputPeer reply_to:flags.0?InputReplyTo multi_media:Vector<InputSingleMedia> schedule_date:flags.10?int send_as:flags.13?InputPeer quick_reply_shortcut:flags.17?InputQuickReplyShortcut effect:flags.18?long allow_paid_stars:flags.21?long = Updates;
```

The update_stickersets_order flag should be set when manually choosing and using stickers, masks and custom emojis from a specific stickerset in the stickerset selection bar (not through suggested or recent stickersets UI views).
Note that for custom emojis, the flag should only be set when manually choosing custom emojis from a single custom emoji stickerset (not multiple custom emoji stickersets).

Setting this flag will trigger an updateMoveStickerSetToTop update (instead of the usual updateStickerSetsOrder/updateStickerSets updates), indicating that the installed stickerset list was reordered and the specified stickerset was moved to the top.

Note that the API also offers a separate list of recent stickers (not stickersets), see here » for more info.

### Emoji categories

The sticker selection UI should offer a list of categories to quickly filter results by a (list of) emojis, or by some other criteria, see here » for more info.

### Sticker suggestions

```
messages.stickersNotModified#f1749a22 = messages.Stickers;
messages.stickers#30a6ec7e hash:long stickers:Vector<Document> = messages.Stickers;

emojiListNotModified#481eadfa = EmojiList;
emojiList#7a1e11d1 hash:long document_id:Vector<long> = EmojiList;

---functions---

messages.getStickers#d5a5d3a1 emoticon:string hash:long = messages.Stickers;
messages.searchCustomEmoji#2c11c0d7 emoticon:string hash:long = EmojiList;
```

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

### Special stickers

```
messages.stickersNotModified#f1749a22 = messages.Stickers;
messages.stickers#30a6ec7e hash:long stickers:Vector<Document> = messages.Stickers;

---functions---

messages.getStickers#d5a5d3a1 emoticon:string hash:long = messages.Stickers;
```

Some places in the UI require the usage of a server-specified list of stickers, independent from the installed stickersets, that may be fetched from the server using messages.getStickers and a specific value of emoticon.

#### Premium sticker examples

Some places in the UI might require showing a list of Premium stickers, as an example of stickers that may be used if the user buys a Premium subscription.

To fetch this special list, invoke messages.getStickers with emoticon=

#### Greeting stickers

When the user opens a private chat with a user they don't have a history with, the UI should display a randomly chosen greeting sticker+invitation to send a message.

To fetch this special list of greeting stickers, invoke messages.getStickers with emoticon=.

Note that if a custom Telegram Business introduction » is enabled, the message+sticker specified in userFull.intro must be used, instead.

### Attached stickers

```
inputMediaUploadedPhoto#1e287d04 flags:# spoiler:flags.2?true file:InputFile stickers:flags.0?Vector<InputDocument> ttl_seconds:flags.1?int = InputMedia;

inputMediaUploadedDocument#37c9330 flags:# nosound_video:flags.3?true force_file:flags.4?true spoiler:flags.5?true file:InputFile thumb:flags.2?InputFile mime_type:string attributes:Vector<DocumentAttribute> stickers:flags.0?Vector<InputDocument> video_cover:flags.6?InputPhoto video_timestamp:flags.7?int ttl_seconds:flags.1?int = InputMedia;

photo#fb197a65 flags:# has_stickers:flags.0?true id:long access_hash:long file_reference:bytes date:int sizes:Vector<PhotoSize> video_sizes:flags.1?Vector<VideoSize> dc_id:int = Photo;

document#8fd4c4d8 flags:# id:long access_hash:long file_reference:bytes date:int mime_type:string size:long thumbs:flags.0?Vector<PhotoSize> video_thumbs:flags.1?Vector<VideoSize> dc_id:int attributes:Vector<DocumentAttribute> = Document;
documentAttributeHasStickers#9801d2f7 = DocumentAttribute;

inputStickeredMediaPhoto#4a992157 id:InputPhoto = InputStickeredMedia;
inputStickeredMediaDocument#438865b id:InputDocument = InputStickeredMedia;

inputStickerSetItem#32da9e9c flags:# document:InputDocument emoji:string mask_coords:flags.0?MaskCoords keywords:flags.1?string = InputStickerSetItem;

stickerSetCovered#6410a5d2 set:StickerSet cover:Document = StickerSetCovered;
stickerSetMultiCovered#3407e51b set:StickerSet covers:Vector<Document> = StickerSetCovered;

---functions---

messages.sendMedia#ac55d9c1 flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true allow_paid_floodskip:flags.19?true peer:InputPeer reply_to:flags.0?InputReplyTo media:InputMedia message:string random_id:long reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.10?int send_as:flags.13?InputPeer quick_reply_shortcut:flags.17?InputQuickReplyShortcut effect:flags.18?long allow_paid_stars:flags.21?long suggested_post:flags.22?SuggestedPost = Updates;

messages.getAttachedStickers#cc5b67cc media:InputStickeredMedia = Vector<StickerSetCovered>;
```

Stickers of all kinds can be attached to photos and videos.
First, overlay the sticker on top of the media file locally (properly handling eventual default mask coordinates), and upload the modified media file.
Then, when sending the media file using messages.sendMedia, indicate the stickers that were overlaid in the stickers field of inputMediaUploadedPhoto or inputMediaUploadedDocument.

Sent stickered photos will have the has_stickers flag set.
Sent stickered video documents will have a documentAttributeHasStickers attribute.

When receiving such a media file, clients should call messages.getAttachedStickers, passing the media: the method will return a set of stickerset previews », with info about the stickersets (not stickers) used in the media.

#### Mask stickers

Mask stickers are a special kind of static stickers that are meant to be overlaid on top of photos and attached to media, as specified here ».

```
maskCoords#aed6dbb2 n:int x:double y:double zoom:double = MaskCoords;

documentAttributeSticker#6319d612 flags:# mask:flags.1?true alt:string stickerset:InputStickerSet mask_coords:flags.0?MaskCoords = DocumentAttribute;

inputStickerSetItem#32da9e9c flags:# document:InputDocument emoji:string mask_coords:flags.0?MaskCoords keywords:flags.1?string = InputStickerSetItem;

---functions---

messages.getMaskStickers#640f82b8 hash:long = messages.AllStickers;
```

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

