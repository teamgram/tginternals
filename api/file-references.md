# File references

File references are strings of bytes, that can be encountered in the file_reference fields of document and photo objects.

They must be cached by the client, along with the origin where the document/photo object was found, in order to be refetched when the file reference expires.

Example implementation of a reference database: MadelineProto, android, telegram desktop, tdlib.

Implementation and maintenance of the file reference database may be fully automated by using the file reference database schema generator tool », and the file reference database map file it generates.

Latest file reference database map file for the current layer »

Dictionary:

- A file reference path is a deserialization path where a file_reference field may appear, for example updateNewMessage.message -> message.media -> messageMediaDocument.document -> document.file_reference.

- A file reference origin (or FileSource) contains information that the client may use to re-fetch the document (and the new file reference), for example for the above path it's getMessage{peer: updateNewMessage.message.peer, id: updateNewMessage.message.id}, which can be used to refetch the document using either messages.getMessages or channels.getMessages depending on the type of the Peer.

The database map file contains all possible origins, for all possible file reference paths.

It is automatically generated and validated by the file reference database schema generator tool »; this tool can be manually run on newer or experimental layers, to generate the file reference database map file for a given API schema: see here » for more info.

### Implementation

Here's how to use file reference database map file to generate all the logic needed for a file reference database within an MTProto client.

The file reference database can be represented by the following type:

```
HashMap<FileId, Vector<FileSource>>
```

It maps a FileId to one or more objects of type FileSource: the exact structure and possible types of FileId and FileSource are specified within the map file.

New entries are added when deserializing objects of a specific type received from the API, mapping a received file ID to one or more FileSources; the exact procedure and affected objects are fully specified within the map file.

Later, when a file is used (for example when sending or downloading a media file), and a FILE_REFERENCE_EXPIRED RPC error is received for a specific FileId, the client must fetch the List<FileSource> associated to the used FileId, and execute a specific method call for each FileSource, until a new file_reference is fetched for the FileId.

Note that the database doesn't have to store the actual file_reference, only the file id => file source mapping: the file reference itself can be stored for example in the message DB, or the document DB, or in any other way that can be associated to a FileId upon extraction or storage as specified in the map file.

The map file itself follows a custom TL schema, and is available in JSON or serialized TL format.

Serialized TL version of map file »

JSON map file » - The constructor predicate is serialized under the _ key, bytes fields are serialized as {"_": "bytes", "bytes": "<base64 encoded value>"}

TL schema of map file »

JSON version of TL schema of map file »

This is the TL schema of the map file:

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
true#3fedd339 = True;

vector#1cb5c415 {t:Type} # [ t ] = Vector t;

// Root
fileReferenceOrigins#ed01a4f1 db_schema:string db_schema_json:string locations:Vector<Location> origins:Vector<Origin> skipped:Vector<SkippedOrigin> actions:Vector<Action> = FileReferenceOrigins;

locationIncoming#e18770f4 predicate:string stored_constructor:string = Location;
locationOutgoing#e7740ae0 predicate:string stored_constructor:string = Location;

origin#b62177bf flags:# predicate:string is_constructor:flags.0?true stored_constructor:string stored_params:Vector<FieldExtractor> skipped_flags:Vector<string> needs_parent:flags.3?string parent_is_constructor:flags.4?true = origin;

skippedOrigin#7c62809e flags:# predicate:string is_constructor:flags.0?true why:string = SkippedOrigin;

action#9539f410 stored_constructor:string action:ActionOp = Action;

// Field extraction path
paramNotFlag#acd9d5cf = ParamFlag;
paramIsFlagAbortIfEmpty#f8fe9fee = ParamFlag;
paramIsFlagFallback#202b77a1 fallback:TypedOp = ParamFlag;
paramIsFlagPassthrough#1dc6e17d = ParamFlag;

pathPart#8dc6ff46 constructor:string param:string flag:ParamFlag = PathPart;

path#0c3586a2 parts:Vector<PathPart> = Path;
pathParent#58f13684 parts:Vector<PathPart> = Path;

// Extractor
extractAndStore#72069549 from:Path to:string = FieldExtractor;

extractInputStickerSetFromDocumentAttributesAndStore#369d8d14 from:Path to:string = FieldExtractor;
extractInputStickerSetFromStickerSetAndStore#c167d470 from:Path to:string = FieldExtractor;

extractPeerIdFromPeerAndStore#7d33019c from:Path to:string = FieldExtractor;
extractPeerIdFromInputPeerAndStore#a51acfb4 from:Path to:string = FieldExtractor;

extractChannelIdFromChannelAndStore#5675bc97 from:Path to:string = FieldExtractor;
extractChannelIdFromInputChannelAndStore#b662660e from:Path to:string = FieldExtractor;

extractUserIdFromUserAndStore#4778ec63 from:Path to:string = FieldExtractor;
extractUserIdFromInputUserAndStore#7720aa2e from:Path to:string = FieldExtractor;

// Actions
callOp#c2ff3383 method:string args:Vector<TypedOpArg> = ActionOp;
getMessageOp#237849e8 peer:TypedOp id:TypedOp from_scheduled:TypedOp quick_reply_shortcut_id:TypedOp = ActionOp;

// For string => TypedOp dictionaries
typedOpArg#3a2930c2 key:string value:TypedOp = TypedOpArg;

// Typed constructors, the type is specified to simplify codegen,
// but isn't strictly necessary as it can be inferred from the TypedOpOp.
// It is fully pre-validated during the generation of the definition file.
typedOp#705b10ec type:string op:TypedOpOp = TypedOp;

// The actual ops
copyOp#f48f418f from:string = TypedOpOp;

getInputChannelByIdOp#3cb47531 from:string = TypedOpOp;
getInputUserByIdOp#c0ee4326 from:string = TypedOpOp;
getInputPeerByIdOp#19813750 from:string = TypedOpOp;

// Literals & constructors (methods not allowed or needed here)
constructorOp#107f8d8a constructor:string args:Vector<TypedOpArg> = TypedOpOp;

vectorOp#f8fb8f72 values:Vector<TypedOp> = TypedOpOp;

intLiteralOp#cbfabe7c value:int = TypedOpOp;
longLiteralOp#d08b8d3a value:long = TypedOpOp;
stringLiteralOp#2b56ea8e value:string = TypedOpOp;
bytesLiteralOp#fdb395a4 value:bytes = TypedOpOp;
boolLiteralOp#37e07911 value:Bool = TypedOpOp;
doubleLiteralOp#3651e3bf value:double = TypedOpOp;
themeFormatLiteralOp#8e4f9208 = TypedOpOp;
```

Current values for the current layer:

DB schema:

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
true#3fedd339 = True;
vector#1cb5c415 {t:Type} # [ t ] = Vector t;

fileIdPhoto#47a0bd49 id:long = FileId;
fileIdDocument#461b1d89 id:long = FileId;

fileSourceMessage#7e015bb0 flags:# from_scheduled:flags.0?true quick_reply_shortcut_id:flags.1?int peer:long id:int = FileSource;
fileSourceStarsTransaction#c1bac8c7 flags:# peer:long id:string refund:flags.0?true ton:flags.1?true = FileSource;
fileSourceStory#c820e3eb id:int peer:long = FileSource;
fileSourceWebPage#9e5b749c url:string = FileSource;
fileSourceBotApp#01cf8b7a id:long access_hash:long = FileSource;
fileSourceUserFull#70fdb7b0 id:long = FileSource;
fileSourceAdminLog#4797f959 channel:long max_id:long = FileSource;
fileSourceStoryAlbum#5e01f223 peer:long = FileSource;
fileSourceBotPreviewMedia#0aa91441 bot:long = FileSource;
fileSourceBotPreviewInfo#f9d2d6fc bot:long lang_code:string = FileSource;
fileSourcePaidMedia#b18d9042 id:int peer:long = FileSource;
fileSourceSavedMusic#dd1a7664 user_id:long id:long access_hash:long = FileSource;
fileSourceChatFull#9de75fde chat_id:long = FileSource;
fileSourceChannelFull#6fe19339 channel:long = FileSource;
fileSourcePremiumPromo#c907a44f = FileSource;
fileSourceAttachMenuBot#c3002694 bot:long = FileSource;
fileSourceTheme#92d05e0c id:long access_hash:long = FileSource;
fileSourceWallPaper#50dbf2f7 id:long access_hash:long = FileSource;
fileSourceStickerSet#34c73709 stickerset:InputStickerSet = FileSource;
fileSourceSavedGifs#13e78e07 = FileSource;
fileSourceSavedRingtones#2b25ef1b = FileSource;
fileSourceAvailableEffects#eb8578f0 = FileSource;
fileSourceAvailableReactions#0e432388 = FileSource;
fileSourceUserProfilePhoto#e39ee274 user_id:long max_id:long = FileSource;
fileSourceDocumentByHash#0f151e0f sha256:bytes size:long mime_type:string = FileSource;
```

Locations:

- inputPhoto - fileIdPhoto (outgoing)

- inputDocument - fileIdDocument (outgoing)

- inputDocumentFileLocation - fileIdDocument (outgoing)

- inputPhotoFileLocation - fileIdPhoto (outgoing)

- document - fileIdDocument (incoming)

- photo - fileIdPhoto (incoming)

Actions:

- fileSourceMessage - getMessageOp(peer: getInputPeerByIdOp(peer), id: copyOp(id), from_scheduled: copyOp(from_scheduled)quick_reply_shortcut_id: copyOp(quick_reply_shortcut_id))

- fileSourceStory - stories.getStoriesByID(id: [copyOp(id)], peer: getInputPeerByIdOp(peer))

- fileSourceWebPage - messages.getWebPage(url: copyOp(url), hash: 0)

- fileSourceBotApp - messages.getBotApp(app: inputBotAppID{id: copyOp(id), access_hash: copyOp(access_hash)}, hash: 0)

- fileSourceUserFull - users.getFullUser(id: getInputUserByIdOp(id))

- fileSourceAdminLog - channels.getAdminLog(channel: getInputChannelByIdOp(channel), max_id: copyOp(max_id), min_id: copyOp(max_id), limit: 1, q: "")

- fileSourceStoryAlbum - stories.getAlbums(peer: getInputPeerByIdOp(peer), hash: 0)

- fileSourceBotPreviewMedia - bots.getPreviewMedias(bot: getInputUserByIdOp(bot))

- fileSourceBotPreviewInfo - bots.getPreviewInfo(bot: getInputUserByIdOp(bot), lang_code: copyOp(lang_code))

- fileSourcePaidMedia - messages.getExtendedMedia(id: [copyOp(id)], peer: getInputPeerByIdOp(peer))

- fileSourceSavedMusic - users.getSavedMusicByID(id: getInputUserByIdOp(user_id), documents: [inputDocument{id: copyOp(id), access_hash: copyOp(access_hash), file_reference: base64_decode("")}])

- fileSourceChatFull - messages.getFullChat(chat_id: copyOp(chat_id))

- fileSourceChannelFull - channels.getFullChannel(channel: getInputChannelByIdOp(channel))

- fileSourcePremiumPromo - help.getPremiumPromo()

- fileSourceStarsTransaction - payments.getStarsTransactionsByID(peer: getInputPeerByIdOp(peer), ton: copyOp(ton), id: [inputStarsTransaction{id: copyOp(id), refund: copyOp(refund)}])

- fileSourceAttachMenuBot - messages.getAttachMenuBot(bot: getInputUserByIdOp(bot))

- fileSourceTheme - account.getTheme(theme: inputTheme{id: copyOp(id), access_hash: copyOp(access_hash)}, format: $themeFormat)

- fileSourceWallPaper - account.getWallPaper(wallpaper: inputWallPaper{id: copyOp(id), access_hash: copyOp(access_hash)})

- fileSourceStickerSet - messages.getStickerSet(stickerset: copyOp(stickerset), hash: 0)

- fileSourceSavedGifs - messages.getSavedGifs(hash: 0)

- fileSourceSavedRingtones - account.getSavedRingtones(hash: 0)

- fileSourceAvailableEffects - messages.getAvailableEffects(hash: 0)

- fileSourceAvailableReactions - messages.getAvailableReactions(hash: 0)

- fileSourceUserProfilePhoto - photos.getUserPhotos(user_id: getInputUserByIdOp(user_id), offset: -1, max_id: copyOp(max_id), limit: 1)

- fileSourceDocumentByHash - messages.getDocumentByHash(sha256: copyOp(sha256), size: copyOp(size), mime_type: copyOp(mime_type))

Origins:

- message - fileSourceMessage{from_scheduled: message.from_scheduled?passthrough, quick_reply_shortcut_id: message.quick_reply_shortcut_id?passthrough, peer: extractPeerIdFromPeerAndStore(message.peer_id), id: message.id}

- messageService - fileSourceMessage{peer: extractPeerIdFromPeerAndStore(messageService.peer_id), id: messageService.id, from_scheduled: false, quick_reply_shortcut_id: false}

- (1) storyItem - (needs stories.getPinnedStories) fileSourceStory{id: storyItem.id, peer: extractPeerIdFromInputPeerAndStore(stories.getPinnedStories.peer)}

- (2) storyItem - (needs stories.getStoriesArchive) fileSourceStory{id: storyItem.id, peer: extractPeerIdFromInputPeerAndStore(stories.getStoriesArchive.peer)}

- (3) storyItem - (needs stories.getStoriesByID) fileSourceStory{id: storyItem.id, peer: extractPeerIdFromInputPeerAndStore(stories.getStoriesByID.peer)}

- (4) storyItem - (needs stories.getAlbumStories) fileSourceStory{id: storyItem.id, peer: extractPeerIdFromInputPeerAndStore(stories.getAlbumStories.peer)}

- (5) storyItem - (needs peerStories) fileSourceStory{id: storyItem.id, peer: extractPeerIdFromPeerAndStore(peerStories.peer)}

- (6) storyItem - fileSourceStory{id: storyItem.id, peer: extractPeerIdFromPeerAndStore(storyItem.from_id?abort_if_empty)}

- storyViewPublicRepost - fileSourceStory{id: storyViewPublicRepost.story.storyItem.id, peer: extractPeerIdFromPeerAndStore(storyViewPublicRepost.peer_id)}

- storyReactionPublicRepost - fileSourceStory{id: storyReactionPublicRepost.story.storyItem.id, peer: extractPeerIdFromPeerAndStore(storyReactionPublicRepost.peer_id)}

- foundStory - fileSourceStory{id: foundStory.story.storyItem.id, peer: extractPeerIdFromPeerAndStore(foundStory.peer)}

- publicForwardStory - fileSourceStory{id: publicForwardStory.story.storyItem.id, peer: extractPeerIdFromPeerAndStore(publicForwardStory.peer)}

- webPageAttributeStory - fileSourceStory{id: webPageAttributeStory.story?abort_if_empty.storyItem.id, peer: extractPeerIdFromPeerAndStore(webPageAttributeStory.peer)}

- messageMediaStory - fileSourceStory{id: messageMediaStory.story?abort_if_empty.storyItem.id, peer: extractPeerIdFromPeerAndStore(messageMediaStory.peer)}

- webPage - fileSourceWebPage{url: webPage.url}

- botApp - fileSourceBotApp{id: botApp.id, access_hash: botApp.access_hash}

- botInfo - fileSourceUserFull{id: botInfo.user_id?abort_if_empty}

- channelAdminLogEvent - (needs channels.getAdminLog) fileSourceAdminLog{channel: extractChannelIdFromInputChannelAndStore(channels.getAdminLog.channel), max_id: channelAdminLogEvent.id}

- stories.createAlbum - fileSourceStoryAlbum{peer: extractPeerIdFromInputPeerAndStore(stories.createAlbum.peer)}

- stories.getAlbums - fileSourceStoryAlbum{peer: extractPeerIdFromInputPeerAndStore(stories.getAlbums.peer)}

- stories.updateAlbum - fileSourceStoryAlbum{peer: extractPeerIdFromInputPeerAndStore(stories.updateAlbum.peer)}

- bots.getPreviewMedias - fileSourceBotPreviewMedia{bot: extractUserIdFromInputUserAndStore(bots.getPreviewMedias.bot)}

- bots.getPreviewInfo - fileSourceBotPreviewInfo{bot: extractUserIdFromInputUserAndStore(bots.getPreviewInfo.bot), lang_code: bots.getPreviewInfo.lang_code}

- bots.addPreviewMedia - fileSourceBotPreviewInfo{bot: extractUserIdFromInputUserAndStore(bots.addPreviewMedia.bot), lang_code: bots.addPreviewMedia.lang_code}

- bots.editPreviewMedia - fileSourceBotPreviewInfo{bot: extractUserIdFromInputUserAndStore(bots.editPreviewMedia.bot), lang_code: bots.editPreviewMedia.lang_code}

- updateMessageExtendedMedia - fileSourcePaidMedia{id: updateMessageExtendedMedia.msg_id, peer: extractPeerIdFromPeerAndStore(updateMessageExtendedMedia.peer)}

- (1) userFull - fileSourceUserFull{id: userFull.id}

- (2) userFull - fileSourceSavedMusic{user_id: userFull.id, id: userFull.saved_music?abort_if_empty.document.id, access_hash: userFull.saved_music?abort_if_empty.document.access_hash}

- chatFull - fileSourceChatFull{chat_id: chatFull.id}

- channelFull - fileSourceChannelFull{channel: channelFull.id}

- help.getPremiumPromo - fileSourcePremiumPromo{}

- (1) starsTransaction - (needs payments.getStarsStatus) fileSourceStarsTransaction{peer: extractPeerIdFromInputPeerAndStore(payments.getStarsStatus.peer), ton: payments.getStarsStatus.ton?passthrough, id: starsTransaction.id, refund: starsTransaction.refund?passthrough}

- (2) starsTransaction - (needs payments.getStarsTransactions) fileSourceStarsTransaction{peer: extractPeerIdFromInputPeerAndStore(payments.getStarsTransactions.peer), ton: payments.getStarsTransactions.ton?passthrough, id: starsTransaction.id, refund: starsTransaction.refund?passthrough}

- (3) starsTransaction - (needs payments.getStarsTransactionsByID) fileSourceStarsTransaction{peer: extractPeerIdFromInputPeerAndStore(payments.getStarsTransactionsByID.peer), ton: payments.getStarsTransactionsByID.ton?passthrough, id: starsTransaction.id, refund: starsTransaction.refund?passthrough}

- (4) starsTransaction - (needs payments.getStarsSubscriptions) fileSourceStarsTransaction{peer: extractPeerIdFromInputPeerAndStore(payments.getStarsSubscriptions.peer), id: starsTransaction.id, refund: starsTransaction.refund?passthrough, ton: false}

- attachMenuBot - fileSourceAttachMenuBot{bot: attachMenuBot.bot_id}

- theme - fileSourceTheme{id: theme.id, access_hash: theme.access_hash}

- wallPaper - fileSourceWallPaper{id: wallPaper.id, access_hash: wallPaper.access_hash}

- stickerSetMultiCovered - fileSourceStickerSet{stickerset: extractInputStickerSetFromStickerSetAndStore(stickerSetMultiCovered.set)}

- stickerSetFullCovered - fileSourceStickerSet{stickerset: extractInputStickerSetFromStickerSetAndStore(stickerSetFullCovered.set)}

- messages.stickerSet - fileSourceStickerSet{stickerset: extractInputStickerSetFromStickerSetAndStore(messages.stickerSet.set)}

- messages.savedGifs - fileSourceSavedGifs{}

- account.savedRingtones - fileSourceSavedRingtones{}

- account.savedRingtoneConverted - fileSourceSavedRingtones{}

- account.uploadRingtone - fileSourceSavedRingtones{}

- messages.availableEffects - fileSourceAvailableEffects{}

- messages.availableReactions - fileSourceAvailableReactions{}

- photo - (needs photos.getUserPhotos) fileSourceUserProfilePhoto{user_id: extractUserIdFromInputUserAndStore(photos.getUserPhotos.user_id), max_id: photo.id}

- photos.updateProfilePhoto - fileSourceUserProfilePhoto{user_id: extractUserIdFromInputUserAndStore(photos.updateProfilePhoto.bot?fallback(inputUserSelf{})), max_id: photos.updateProfilePhoto.(return value).photos.photo.photo.photo.id}

- photos.uploadProfilePhoto - fileSourceUserProfilePhoto{user_id: extractUserIdFromInputUserAndStore(photos.uploadProfilePhoto.bot?fallback(inputUserSelf{})), max_id: photos.uploadProfilePhoto.(return value).photos.photo.photo.photo.id}

- photos.uploadContactProfilePhoto - fileSourceUserProfilePhoto{user_id: extractUserIdFromInputUserAndStore(photos.uploadContactProfilePhoto.user_id), max_id: photos.uploadContactProfilePhoto.(return value).photos.photo.photo.photo.id}

- (1) document - fileSourceStickerSet{stickerset: extractInputStickerSetFromDocumentAttributesAndStore(document.attributes)}

- (2) document - (needs users.getSavedMusic) fileSourceSavedMusic{user_id: extractUserIdFromInputUserAndStore(users.getSavedMusic.id), id: document.id, access_hash: document.access_hash}

- (3) document - (needs users.getSavedMusicByID) fileSourceSavedMusic{user_id: extractUserIdFromInputUserAndStore(users.getSavedMusicByID.id), id: document.id, access_hash: document.access_hash}

- messages.getDocumentByHash - fileSourceDocumentByHash{sha256: messages.getDocumentByHash.sha256, size: messages.getDocumentByHash.size, mime_type: messages.getDocumentByHash.mime_type}

Skipped:

- messages.getSponsoredMessages - Do not store file references from sponsored messages

- help.getAppUpdate - Don't handle file references from ephemeral app update info

- help.getRecentMeUrls - Don't handle file references from recent t.me URLs

- recentMeUrlChatInvite - Do not store references based on chat invite links

- messages.checkChatInvite - Do not store references based on chat invite links

- messages.getInlineBotResults - Inline bot results are ephemeral

- messages.getPreparedInlineMessage - Inline bot results are ephemeral

- messages.uploadMedia - A freshly uploaded media file will obtain a context only once it is sent to a chat

- messages.uploadImportedMedia - A freshly uploaded media file will obtain a context only once it is sent to a chat

- updateServiceNotification - Cannot refetch service notifications

- messages.getWebPagePreview - No locations are added for the method call, as it doesn't use persistent IDs as input; the location is instead extracted from the persistent IDs in the returned WebPage object

- payments.resaleStarGifts - Contexts for star gifts are not yet implemented

- payments.starGiftUpgradePreview - Contexts for star gifts are not yet implemented

- starGift - Contexts for star gifts are not yet implemented

- starGiftUnique - Contexts for star gifts are not yet implemented

- starGiftCollection - Contexts for star gifts are not yet implemented

- payments.starGiftCollections - Contexts for star gifts are not yet implemented

- messages.getCustomEmojiDocuments - Do not store file references in this context

- account.uploadTheme - A freshly uploaded theme file will obtain a context only once it is created via account.createTheme

Here's a detailed description of the constructors.

#### Root

```
fileReferenceOrigins#ed01a4f1 db_schema:string db_schema_json:string locations:Vector<Location> origins:Vector<Origin> skipped:Vector<SkippedOrigin> actions:Vector<Action> = FileReferenceOrigins;

locationIncoming#e18770f4 predicate:string stored_constructor:string = Location;
locationOutgoing#e7740ae0 predicate:string stored_constructor:string = Location;

origin#b62177bf flags:# predicate:string is_constructor:flags.0?true stored_constructor:string stored_params:Vector<FieldExtractor> skipped_flags:Vector<string> needs_parent:flags.3?string parent_is_constructor:flags.4?true = origin;

skippedOrigin#7c62809e flags:# predicate:string is_constructor:flags.0?true why:string = SkippedOrigin;

action#9539f410 stored_constructor:string action:ActionOp = Action;
```

The map file is composed of a single fileReferenceOrigins constructor, which contains:

- The db_schema and db_schema_json fields with the TL database schema of FileIds and FileSources.

- db_schema is text TL schema, db_schema_json is the same TL schema in the JSON format also used for the API schema ».

- A list of Location constructors, containing the full list of constructors that have a file_reference field, and info on how to generate a FileId from them.

- A list of origin constructors, containing instructions on how to generate FileSources from received constructors or method responses.

- A list of action constructors, containing the method call to invoke when refreshing a file reference using a previously stored FileId and FileSource.

- A list of skippedOrigin constructors.

- These constructors indicate that the origin should be ignored completely (including during codegen): skippedOrigin origins are used internally to make sure all file reference paths are still covered in some way during validation, including paths for ephemeral media like inline results, or for media without any associated origin (for example, media uploaded using messages.uploadMedia but not yet sent anywhere obviously does not have any associated origin).

- skippedOrigin.predicate - Indicates the name of the ignored constructor or method.

- skippedOrigin.is_constructor - If set, predicate points to a constructor, otherwise it points to a method.

- skippedOrigin.why - A human-readable reason as to why this origin should be ignored.

- Each skipped predicate can have one associated reason.

#### Locations

```
locationIncoming#e18770f4 predicate:string stored_constructor:string = Location;
locationOutgoing#e7740ae0 predicate:string stored_constructor:string = Location;
```

Locations contain the full list of constructors (never methods) that have a file_reference and an id field.

The id field of predicate must be used to generate a FileId object of type stored_constructor.

locationIncoming references constructors that can only be received from the API.
locationOutgoing references constructors that can only be sent to the API.

Params:

- predicate - The name of the API constructor.

- stored_constructor - The name of the FileId object to be used for database read/writes.

Each unique predicate can only have one stored_constructor.

For example, current API layers have the following locations:

- photo => fileIdPhoto (incoming)

- document => fileIdDocument (incoming)

- inputPhoto => fileIdPhoto (outgoing)

- inputPhotoFileLocation => fileIdPhoto (outgoing)

- inputDocument => fileIdDocument (outgoing)

- inputDocumentFileLocation => fileIdDocument (outgoing)

When encountering one of the objects on the left, use the id field to generate a FileId of the type on the right.

When refreshing references, replace the file_reference field of the object on the left.

(Legacy inputFileLocation constructors are ignored by the current map file).

#### Origin

```
origin#b62177bf flags:# predicate:string is_constructor:flags.0?true stored_constructor:string stored_params:Vector<FieldExtractor> skipped_flags:Vector<string> needs_parent:flags.3?string parent_is_constructor:flags.4?true = origin;
```

An origin contains instructions on how to extract and store file reference origins from an incoming method response or update.

Note: The following sections assume that all Updates constructors have already been converted to a vector of Update constructors, including short variants like updateShortMessage, updateShortSentMessage, updateShortChatMessage, which must be pre-converted to Update constructors by the client using information extracted from the method call.
While this operation could be done within the map file, it would needlessly increase the number of paths: given that most clients already convert short constructors to Update constructors, the map file only considers paths starting from the Update constructors.

Parameters:

- predicate - Indicates the name of the constructor or of the method where extraction of the origin fields must start.

- is_constructor - If set, predicate points to a constructor, otherwise it points to a method.

- needs_parent - If set, contains the name of a constructor which needs to appear as a parent in the deserialized object or a method whose response we're deserializing, as it will be used by one or more of the paths in the action.

- parent_is_constructor - If set, needs_parent points to a constructor; otherwise it points to a method.

- stored_constructor - Contains the name of a FileSource constructor from the TL schema specified in fileReferenceOrigins.db_schema, which should be stored to the database after being populated by stored_params as specified below.

- stored_params - Contains info on how to populate the FileSource constructor specified in stored_constructor

- skipped_flags - In some cases, some flag fields of stored_constructor aren't referenced by action: this field contains the full list of flags which are never referenced by the current origin and must be unset.

Each unique predicate can have one or more stored_constructors with different params.

If the is_constructor flag is set, when deserializing a constructor with predicate equal to predicate, contained in an incoming Update or in at any depth in a method call response, do the following:

- Before beginning deserialization of the constructor, push a new FileSource of type stored_constructor to the file source stack.

- Skip pushing the FileSource if needs_parent is set but we don't have a constructor or method of type needs_parent in our parents.

- During deserialization, associate all encountered FileIds (generated according to the locations schema) to all sources of all types currently on the stack.

- After deserialization of the constructor, pop the pushed FileSource of type stored_constructor, make sure it can be processed according to stored_params (all required flag fields are set, all paths can be correctly extracted), and if yes, populate the FileSource of type stored_constructor accordingly and commit the origin to the database (using the FileIds associated at step 2 as keys, and stored_constructor as value).

- Skip this step if needs_parent is set but we don't have a constructor or method of type needs_parent in our parents.

If the is_constructor flag is not set, when deserializing the response of the method with name equal to predicate, do the following:

- Before beginning deserialization of the method response, push a new FileSource of type stored_constructor to the file source stack.

- During deserialization, associate all encountered FileIds (generated according to the locations schema) to all sources of all types currently on the stack.

- After deserialization of the method response, pop the pushed FileSource of type stored_constructor, make sure it can be processed according to stored_params (all required flag fields are set, all paths can be correctly extracted), and if yes, populate the FileSource of type stored_constructor accordingly and commit the origin to the database (using the FileIds associated at step 2 as keys, and stored_constructor as value).

Note that method origins cannot make use of needs_parent.

#### Field extraction

```
// Extractor
extractAndStore#72069549 from:Path to:string = FieldExtractor;

extractInputStickerSetFromDocumentAttributesAndStore#369d8d14 from:Path to:string = FieldExtractor;
extractInputStickerSetFromStickerSetAndStore#c167d470 from:Path to:string = FieldExtractor;

extractPeerIdFromPeerAndStore#7d33019c from:Path to:string = FieldExtractor;
extractPeerIdFromInputPeerAndStore#a51acfb4 from:Path to:string = FieldExtractor;

extractChannelIdFromChannelAndStore#5675bc97 from:Path to:string = FieldExtractor;
extractChannelIdFromInputChannelAndStore#b662660e from:Path to:string = FieldExtractor;

extractUserIdFromUserAndStore#4778ec63 from:Path to:string = FieldExtractor;
extractUserIdFromInputUserAndStore#7720aa2e from:Path to:string = FieldExtractor;

// Paths
paramNotFlag#acd9d5cf = ParamFlag;
paramIsFlagAbortIfEmpty#f8fe9fee = ParamFlag;
paramIsFlagFallback#202b77a1 fallback:TypedOp = ParamFlag;
paramIsFlagPassthrough#1dc6e17d = ParamFlag;

pathPart#8dc6ff46 constructor:string param:string flag:ParamFlag = PathPart;

path#c3586a2 parts:Vector<PathPart> = Path;
pathParent#58f13684 parts:Vector<PathPart> = Path;
```

Field extractors are used to extract a parameter from one or more constructors, i.e. updateStory.story -> storyItem.media -> messageMediaDocument.document -> document.file_reference and store it to the specified field of a FileSource.

##### Extractors

```
extractAndStore#72069549 from:Path to:string = FieldExtractor;

extractInputStickerSetFromDocumentAttributesAndStore#369d8d14 from:Path to:string = FieldExtractor;
extractInputStickerSetFromStickerSetAndStore#c167d470 from:Path to:string = FieldExtractor;

extractPeerIdFromPeerAndStore#7d33019c from:Path to:string = FieldExtractor;
extractPeerIdFromInputPeerAndStore#a51acfb4 from:Path to:string = FieldExtractor;

extractChannelIdFromChannelAndStore#5675bc97 from:Path to:string = FieldExtractor;
extractChannelIdFromInputChannelAndStore#b662660e from:Path to:string = FieldExtractor;

extractUserIdFromUserAndStore#4778ec63 from:Path to:string = FieldExtractor;
extractUserIdFromInputUserAndStore#7720aa2e from:Path to:string = FieldExtractor;
```

###### extractAndStore

Extracts the value at the specified path and stores it to $FileSource.$to.

###### extractInputStickerSetFromDocumentAttributesAndStore

Takes the Vector<DocumentAttribute> at from, looks for a documentAttributeSticker, and stores the InputStickerSet contained in documentAttributeSticker.stickerset into $FileSource.$to.

Aborts if there is no attribute of type documentAttributeSticker in the passed vector.

###### extractInputStickerSetFromStickerSetAndStore

Takes the stickerSet at from, transforms it into an InputStickerSet, and stores it into $FileSource.$to.

###### extractPeerIdFromPeerAndStore

Takes the Peer at from, transforms it into a bot API peer ID (of type long) », and stores it into $FileSource.$to.

###### extractPeerIdFromPeerAndStore

Takes the InputPeer at from, transforms it into a bot API peer ID (of type long) », and stores it into $FileSource.$to.

###### extractChannelIdFromChannelAndStore

Takes the channel at from, takes the id field and stores it into $FileSource.$to.

###### extractChannelIdFromInputChannelAndStore

Takes the InputChannel at from, takes the channel_id field and stores it into $FileSource.$to.

Aborts if from points to an inputChannelEmpty.

###### extractUserIdFromUserAndStore

Takes the user at from, takes the id field and stores it into $FileSource.$to.

###### extractUserIdFromInputUserAndStore

Takes the InputUser at from, takes the user_id field and stores it into $FileSource.$to.

If from points to an inputUserSelf, stores the ID of the current user, instead.

Aborts if from points to an inputUserEmpty.

##### Paths

The first part of the path always points to:

- The constructor/method of the origin (origin.predicate), for path

- The constructor/method of the parent contained in origin.needs_parent, for pathParent

A path is composed of multiple pathParts.

Each pathPart contains the following fields, which describe how to extract the field.

- constructor - Indicates the required constructor/method predicate.

- If a different constructor type is encountered (i.e. documentEmpty instead of document), abort extraction.

- By definition, if a method name is passed, it will always be equal to the method of the associated origin.

- param - Indicates the required parameter; if it's an empty string, it indicates the return value of a method.

- flag - Contains exactly one of the following constructors:

- paramNotFlag - The current parameter is not a flag

- paramIsFlagAbortIfEmpty - The current parameter is a flag, and if it's not set, abort extraction.

- paramIsFlagFallback -  The current parameter is a flag, and if it's not set, use the specified TypedOp as fallback value.

- Note that OPs of type copyOp, getInputChannelByIdOp, getInputUserByIdOp and getInputPeerByIdOp are not allowed in this context.

- paramIsFlagPassthrough - The current parameter is a flag, and its value should be copied/returned verbatim; can only be used on the last element of a path and within the arguments of a constructorOp/callOp/getMessageOp only if the argument that uses this path is a flag of the same type.

#### Actions

```
action#9539f410 stored_constructor:string action:ActionOp = Action;

// Actions
callOp#c2ff3383 method:string args:Vector<TypedOpArg> = ActionOp;
getMessageOp#237849e8 peer:TypedOp id:TypedOp from_scheduled:TypedOp quick_reply_shortcut_id:TypedOp = ActionOp;

// For string => TypedOp dictionaries
typedOpArg#3a2930c2 key:string value:TypedOp = TypedOpArg;

// Typed constructors, the type is specified to simplify codegen,
// but isn't strictly necessary as it can be inferred from the TypedOpOp.
// It is fully pre-validated during the generation of the definition file.
typedOp#705b10ec type:string op:TypedOpOp = TypedOp;
```

Actions are used to refresh an expired file reference according to FileSources associated to the FileId (i.e. a FILE_REFERENCE_EXPIRED RPC error is returned when using a file reference).

Params:

- stored_constructor - The name of an object of type FileSource, specified in the db_schema.

- action - The action to execute when refreshing a file source of type stored_constructor.

There can only be one action per constructor.

The arguments of the action are composed of a set of typedOp constructors.

typedOp » is a wrapper for a TypedOpOp constructor which also contains the TL type of the associated TypedOpOp; this isn't strictly necessary for evaluation, but it can be useful during automatic code generation from the definition file.

##### callOp

callOp is a generic action which invokes the method specified in method with the arguments specified in args.

callOp.args will always contain at least all of the required parameters, and possibly some flagged parameters as well.

##### getMessageOp

getMessageOp is a specialized action which invokes either messages.getMessages or channels.getMessages depending on the type of the peer (which is always a subtype of InputPeer), passing the id as the only element to the vector id parameter.
If the flag to which the from_scheduled points is set, messages.getScheduledMessages should be executed instead.
If the flag to which the quick_reply_shortcut_id points is set, messages.getQuickReplyMessages should be executed instead, passing the value of the quick_reply_shortcut_id flag to messages.getQuickReplyMessages.shortcut_id and the id as the only element of a vector, passed to messages.getQuickReplyMessages.id.

#### Action parameters

```
copyOp#f48f418f from:string = TypedOpOp;

getInputChannelByIdOp#3cb47531 from:string = TypedOpOp;
getInputUserByIdOp#c0ee4326 from:string = TypedOpOp;
getInputPeerByIdOp#19813750 from:string = TypedOpOp;

// Literals & constructors (methods not allowed or needed here)
constructorOp#107f8d8a constructor:string args:Vector<TypedOpArg> = TypedOpOp;

vectorOp#f8fb8f72 values:Vector<TypedOp> = TypedOpOp;

intLiteralOp#cbfabe7c value:int = TypedOpOp;
longLiteralOp#d08b8d3a value:long = TypedOpOp;
stringLiteralOp#2b56ea8e value:string = TypedOpOp;
bytesLiteralOp#fdb395a4 value:bytes = TypedOpOp;
boolLiteralOp#37e07911 value:Bool = TypedOpOp;
doubleLiteralOp#3651e3bf value:double = TypedOpOp;
themeFormatLiteralOp#8e4f9208 = TypedOpOp;
```

Action parameters are represented by TypedOpOp constructors.

##### copyOp

The most commonly used type, copies the value(s) from the stored $FileSource.$from.

##### getInputChannelByIdOp

Returns an InputChannel constructor from the client's peer database, based on the channel ID of type long specified in the stored $FileSource.$from.

##### getInputUserByIdOp

Returns an InputUser constructor from the client's peer database, based on the channel ID of type long specified in the stored $FileSource.$from.

##### getInputPeerByIdOp

Returns an InputPeer constructor from the client's peer database, based on the bot API peer ID » of type long specified in the stored $FileSource.$from.

##### constructorOp

Constructs the constructor of type (predicate) constructor using the arguments specified in args.

##### vectorOp

Constructs a vector of the constructors passed in values.

##### intLiteralOp

Constructs a literal int with the value passed in value.

##### longLiteralOp

Constructs a literal long with the value passed in value.

##### stringLiteralOp

Constructs a literal string with the value passed in value.

##### bytesLiteralOp

Constructs a literal bytes with the value passed in value.

##### boolLiteralOp

Constructs a literal Bool with the value passed in value.

##### doubleLiteralOp

Constructs a literal double with the value passed in value.

##### themeFormatLiteralOp

Constructs a string, indicating the theming engines supported by the client (used when working with theme-related media, can be an empty string if the client doesn't support themes).

