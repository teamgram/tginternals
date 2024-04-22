# Uploading and Downloading Files
When working with the API, it is sometimes necessary to send a relatively large file to the server. For example, when sending a message with a photo/video attachment or when setting the current user's profile picture.
### Uploading files
There are a number of API methods to save files. The schema of the types and methods used is presented below:
Before transmitting the contents of the file itself, the file has to be assigned a unique 64-bit client identifier: file_id.
The file's binary content is then split into parts. All parts must have the same size (part_size) and the following conditions must be met:
- part_size % 1024 = 0 (divisible by 1KB)
- 524288 % part_size = 0 (512KB must be evenly divisible by part_size)
The last part does not have to satisfy these conditions, provided its size is less than part_size.
The following appConfig fields specify the maximum number of uploadable file parts:
- upload_max_fileparts_default » - Maximum number of file parts uploadable by non-Premium users.
- upload_max_fileparts_premium » - Maximum number of file parts uploadable by Premium users.
Note that the limit of uploadable file parts does not account for the part_size: thus the total file size limit can only be reached with the biggest possible part_size of 512KB, which is actually the recommended part_size to avoid excessive protocol overhead.
Each part should have a sequence number, file_part, with a value ranging from 0 to the value of the appropriate config parameter minus 1.
After the file has been partitioned you need to choose a method for saving it on the server. Use upload.saveBigFilePart in case the full size of the file is more than 10 MB and upload.saveFilePart for smaller files.
Each call saves a portion of the data in a temporary location on the server to be used later. The storage life of each portion of data is between several minutes and several hours (depending on how busy the storage area is). After this time, the file part will become unavailable.
To increase the time efficiency of a file save operation, we recommend using a (local, i.e. not with invokeAfterMsgs) call queue, so X pieces of the file are being saved at any given moment in time. Each successful operation to save a part invokes the method call to save the next part. The value of X can be tuned to achieve maximum performance.
To further increase performance, multiple parallel call queues (i.e. a tunable number Y of queues) linked to separate TCP connections to the datacenters can be used to upload multiple chunks in parallel.
When using one of the methods mentioned above to save file parts, one of the following data input errors may be returned:
- FILE_PARTS_INVALID - Invalid number of parts. The value is not between 1..upload_max_fileparts_*
- FILE_PART_INVALID: The file part number is invalid. The value is not between 0 and upload_max_fileparts_*-1.
- FILE_PART_TOO_BIG: The size limit (512 KB) for the content of the file part has been exceeded
- FILE_PART_EMPTY: The file part sent is empty
- FILE_PART_SIZE_INVALID - 512KB cannot be evenly divided by part_size
- FILE_PART_SIZE_CHANGED - The part size is different from the size of one of the previous parts in the same file
While the parts are being uploaded, an MD5 hash of the file contents can also be computed to be used later as the md5_checksum parameter in the inputFile constructor (since it is checked only by the server, for encrypted secret chat files it must be generated from the encrypted file).
After the entire file is successfully saved, the final method may be called and passed the generated inputFile object. In case the upload.saveBigFilePart method is used, the inputFileBig constructor must be passed, in other cases use inputFile.
- messages.sendMedia - Sends a media file to a chat
- messages.uploadMedia - Uploads a media file to a chat, without sending it, returning only a MessageMedia constructor that can be used to later send the file to multiple chats, without reuploading it every time.
- photos.uploadProfilePhoto - Used to set a profile or chat picture or video
The file save operation may return one of the following data input errors:
- FILE_PARTS_INVALID: The number of file parts is invalid The value is not between 1 and upload_max_fileparts_*.
- FILE_PART_X_MISSING: Part X (where X is a number) of the file is missing from storage. Try repeating the method call to resave the part.
- MD5_CHECKSUM_INVALID: The file's MD5 checksum did not match the md5_checksum parameter
#### Streamed uploads
The API also supports streamed uploads, in cases where the length of the file is not known before starting the upload.
This is useful for example when converting a video, to avoid buffering the entire converted video on the filesystem, each part is uploaded immediately as soon as it is produced by the encoder.
Everything works similarly to normal uploads, with a few key differences:
- The client buffers part_size bytes (or less if the stream ends) before immediately uploading the part as described in the previous section.
- A total_stream_size variable must be used to keep track of the total number of bytes read from the stream.
- upload.saveBigFilePart must always be used, even if the stream turns out to be smaller than 10MB.
- The file_total_parts field must be set to -1 for all parts except for the last one, using the following logic:
- If the stream ends and the length of the buffered part is bigger than 0, upload it, setting file_total_parts=ceil(total_stream_size/part_size) (like for normal uploads)
- If the stream ends and the length of the buffered part is equal to 0, upload it anyway (upload one last empty part), setting file_total_parts=ceil(total_stream_size/part_size) (like for normal uploads)
Note that streamed uploads cannot be used when uploading photos with inputMediaUploadedPhoto.
#### Albums, grouped media
Telegram allows grouping photos into albums and generic files (audio, docuemnts) into media groups.
To do this, messages.sendMultiMedia is used, wrapping each InputMedia constructor (uploaded or pre-existing, maximum 10 per media group) into an inputSingleMedia constructor, optionally providing a custom per-file caption in message.
For photo albums, clients should display an album caption only if exactly one photo in the group has a caption, otherwise no album caption should be displayed, and only when viewing in detail a specific photo of the group the caption should be shown.
Other grouped media can display a caption under each file.
#### Re-using pre-uploaded files
For some types of documents like GIFs, messages.getDocumentByHash can be used to search for the document on Telegram servers.
The SHA256 hash of the file is computed, and it is passed along with the file's mime type and size to the method: if the file type is correct and the file is found, a document is returned.
### Uploading profile or chat pictures
User profile pictures can be uploaded using the photos.uploadProfilePhoto method: the actual profile picture has to be uploaded as for normal files.
photos.uploadProfilePhoto can also be used to reupload previously uploaded profile pictures.
The optional bot flag can contain info of a bot we own, to change the profile photo of that bot, instead of the current user.
#### Animated profile pictures
Animated profile pictures are also supported, by populating the video flag: square MPEG4 videos up to 1080x1080 are supported, 800x800 is the recommended resolution.
The video_start_ts is a floating point UNIX timestamp in seconds, indicating the frame of the video that should be used as static preview.
Chat, channel and supergroup profile photos and videos can be uploaded using messages.editChatPhoto (basic groups) or channels.editPhoto (channels, supergroups).
Use the inputChatPhoto to reuse previously uploaded profile pictures.
#### Sticker profile pictures
Sticker and custom emoji sticker-based profile pictures are also supported, by populating the video_emoji_markup flag with either a videoSizeStickerMarkup or a videoSizeEmojiMarkup constructor.
The profile picture should be rendered by placing the sticker at the center of a square canvas, in such a way that it occupies at most 67% of it. The background of the canvas is generated from background_colors, which contains a vector of 1, 2, 3 or 4 RBG-24 colors used to generate a solid (1), gradient (2) or freeform gradient (3, 4) background, similar to how fill wallpapers are generated. The rotation angle for gradient backgrounds is 0.
If animated or video stickers/custom emojis are used, the video_start_ts flag can contain a floating point UNIX timestamp in seconds, indicating the frame of the profile picture that should be used as static preview.
account.getDefaultProfilePhotoEmojis may be used to fetch a list of suggested custom emojis that can be used as profile pictures even by non-premium accounts; account.getDefaultGroupPhotoEmojis is the counterpart for group profile pictures.
### Downloading files
There are methods available to download files which have been successfully uploaded. The schema of the types and methods used is presented below:
Any file can be downloaded by calling upload.getFile. 
The data for the input parameter of the InputFileLocation type is generated as follows:
- For photos, inputPhotoFileLocation is used:
- id, file_reference and access_hash taken from the photo constructor
- thumb_size taken from the type field of the desired PhotoSize of the photo
- For profile pictures of users, channels, supergroups and groups, inputPeerPhotoFileLocation has to be used:
- peer is the identifier of the peer whose photo we want to download
- big is used to choose whether to download the full-resolution picture, or just the thumbnail
- photo_id is extracted from the chatPhoto or userProfilePhoto of the desired profile photo
- For documents, inputDocumentFileLocation is used:
- id, file_reference and access_hash taken from the document constructor
- If downloading the thumbnail of a document, thumb_size should be taken from the type field of the desired PhotoSize of the photo; otherwise, provide an empty string.
- For previews of sticker sets, inputStickerSetThumb is used (note: to download stickers and previews of stickers use the document method described above for documents):
- stickerset is set to the InputStickerSet constructor generated from stickerSet
- thumb_version is copied from the same field in stickerSet
- For encrypted secret chat and telegram passport documents, respectively inputEncryptedFileLocation and inputSecureFileLocation have to be used, with parameters extracted from encryptedFile and secureFile (passport docs).
- For livestream chunks, inputGroupCallStream is used:
- call contains the related group call ID+access hash, taken from the groupCall constructor.
- time_ms specifies the timestamp to fetch
- scale specifies the duration of the video segment to fetch in milliseconds, by bitshifting 1000 to the right scale times: duration_ms := 1000 >> scale
- video_channel specifies the video channel to fetch
- video_quality specifies the selected video quality (0 = lowest, 1 = medium, 2 = best)
- For old deprecated photos, if the client has cached some old fileLocations with the deprecated secret identifier, inputFileLocation or inputPhotoLegacyFileLocation is used (this is mainly used for backwards compatibility with bot API file IDs, all user clients must use the modern inputPhotoFileLocation file IDs):
- All fields are taken from the previously cached fileLocation except for file_reference, access_hash and id, which are taken from the photo constructor (the last two fields are used only if available, in which case inputPhotoLegacyFileLocation is used instead of inputFileLocation).
The size of each file in bytes is available, which makes it possible to download the file in parts using the parameters offset and limit, similar to the way files are uploaded.
If precise flag is not specified, then
- The parameter offset must be divisible by 4 KB.
- The parameter limit must be divisible by 4 KB.
- 1048576 (1 MB) must be divisible by limit.
If precise is specified, then
- The parameter offset must be divisible by 1 KB.
- The parameter limit must be divisible by 1 KB.
- limit must not exceed 1048576 (1 MB).
In any case the requested part should be within one 1 MB chunk from the beginning of the file, i. e.
- offset / (1024 * 1024) == (offset + limit - 1) / (1024 * 1024).
When downloading multiple files in parallel from the same DC, clients should limit the parallelism to download at most small_queue_max_active_operations_count/large_queue_max_active_operations_count files in parallel when downloading files smaller/bigger than 20MB (client configuration parameters »).
The file download operation may return a FILE_REFERENCE_EXPIRED error (or another error starting with FILE_REFERENCE_): in this case, the file_reference field of the input location must be refreshed.
The file download operation may return an upload.fileCdnRedirect constructor: in this case, these instructions must be followed for downloading CDN files.
The file download operation may also return one of the following data input errors:
- FILE_ID_INVALID: The file address is invalid
- OFFSET_INVALID: The offset value is invalid
- LIMIT_INVALID: The limit value is invalid
- FILE_MIGRATE_X: The file is in the datacenter No. X
#### Verifying downloaded chunks
In order to confirm the integrity of the downloaded file, clients are recommended to verify hashes for each downloaded part, as for CDN DCs. 
upload.getFileHashes contain FileHash constructors. Each of these constructors contains the SHA-256 hash of a part of the file that starts with offset and takes limit bytes.
Before saving each portion of the data received from the DC into the file, the client can confirm that its hash matches the hash that was received from the master DC. If missing a hash for any file part, client developers must use the upload.getFileHashes method to obtain the missing hash.
#### Handling audio, video and vector previews
Schema:
Telegram attaches a vector of thumbnails with reduced resolution to all uploaded media.
The server also generates a trimmed and scaled down video preview for videos, GIFs and animated profile pictures.
#### Image thumbnail types
Each photo preview has a specific type, indicating the resolution and image transform that was applied server-side.
Special types:
#### Stripped thumbnails
A photoStrippedSize (with type i) is an extremely low-res thumbnail, embedded directly inside media location objects.
It should be shown to the user in chat message previews, or while still downloading the most appropriately sized photoSize through the media DCs as described above.
The stripped bytes payload should be inflated to a JPG payload as seen here ».
#### Vector thumbnails
Messages with animated, video, static stickers can have a compressed svg (< 300 bytes) to show the outline of the sticker before fetching the actual sticker.
Sticker outlines will have a j type photoPathSize thumbnail.
This specific vector thumbnail consists of an SVG path, specially encoded to save space.
This path will be the outline of the animated sticker, and should be shown to the user while downloading the actual sticker.
The payload should be inflated using the following algorithm:
path will contain the actual SVG path that can be directly inserted in the d attribute of an svg <path> element:
#### Video types
A videoSize constructor is typically used for animated profile pictures and video previews.
### Downloading webfiles
Remote HTTP files sent by inline bots in response to inline queries and in other places are represented by WebDocument constructors.
When forwarding such remote HTTP files, they should be sent using external InputMedia constructors.
Remote HTTP files can only be downloaded directly by the client if contained in a webDocumentNoProxy constructor: in this case, the file is deemed safe to download (this is the case for HTTPS files from certain trusted domains).
However, if the remote file is contained in a webDocument, to avoid leaking sensitive information the file must be downloaded through telegram's servers.
This can be done in a manner similar to normal files, with the difference that upload.getWebFile must be used, instead.
The upload.getWebFile method is also used to generate preview pictures for maps and download music file covers, as follows.
Note: the upload.getWebFile query must be sent to the DC specified in the webfile_dc_id MTProto configuration field.
The InputWebFileLocation constructor is generated as follows.
- inputWebFileLocation is simply generated by taking the url and access_hash fields of the webDocument constructor.
- inputWebFileGeoPointLocation is used to download a server-generated image with the map preview from a geoPoint.
- geo_point is generated from the lat, long accuracy_radius parameters of the geoPoint
- access_hash is the access hash of the geoPoint
- w - Map width in pixels before applying scale; 16-1024
- h - Map height in pixels before applying scale; 16-1024
- zoom - Map zoom level; 13-20
- scale - Map scale; 1-3
- inputWebFileAudioAlbumThumbLocation is used to download an album cover with 600x600 resolution for any music file missing embedded album art.
- Note that the document field containing the music file must NOT be provided in secret chats: the locally extracted title and performer fields should be provided, instead.
- In normal chats document should always be provided instead of title and performer, as it has more lax flood limits.
- small if set, downloads a 100x100 thumbnail instead.
- document contains the music file: MUST NOT be provided in secret chats.
- title contains the song title: should only be provided in secret chats.
- performer contains the song performer: should only be provided in secret chats.
### General Considerations
It is recommended that large queries (upload.getFile, upload.saveFilePart, upload.getWebFile) be handled through one or more separate sessions and separate connections, in which no methods other than these should be executed.
This way, data transfer will cause less interference with getting updates and other method calls.
If a media DC with the required DC ID is available (dcOption will have the media flag set), queries must be sent to that DC.
### Related articles
#### Handling file references
How to handle file references.
