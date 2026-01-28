# InputMedia
Defines media content of a message.

```
inputMediaEmpty#9664f57f = InputMedia;
inputMediaUploadedPhoto#1e287d04 flags:# spoiler:flags.2?true file:InputFile stickers:flags.0?Vector<InputDocument> ttl_seconds:flags.1?int = InputMedia;
inputMediaPhoto#b3ba0635 flags:# spoiler:flags.1?true id:InputPhoto ttl_seconds:flags.0?int = InputMedia;
inputMediaGeoPoint#f9c44144 geo_point:InputGeoPoint = InputMedia;
inputMediaContact#f8ab7dfb phone_number:string first_name:string last_name:string vcard:string = InputMedia;
inputMediaUploadedDocument#37c9330 flags:# nosound_video:flags.3?true force_file:flags.4?true spoiler:flags.5?true file:InputFile thumb:flags.2?InputFile mime_type:string attributes:Vector<DocumentAttribute> stickers:flags.0?Vector<InputDocument> video_cover:flags.6?InputPhoto video_timestamp:flags.7?int ttl_seconds:flags.1?int = InputMedia;
inputMediaDocument#a8763ab5 flags:# spoiler:flags.2?true id:InputDocument video_cover:flags.3?InputPhoto video_timestamp:flags.4?int ttl_seconds:flags.0?int query:flags.1?string = InputMedia;
inputMediaVenue#c13d1c11 geo_point:InputGeoPoint title:string address:string provider:string venue_id:string venue_type:string = InputMedia;
inputMediaPhotoExternal#e5bbfe1a flags:# spoiler:flags.1?true url:string ttl_seconds:flags.0?int = InputMedia;
inputMediaDocumentExternal#779600f9 flags:# spoiler:flags.1?true url:string ttl_seconds:flags.0?int video_cover:flags.2?InputPhoto video_timestamp:flags.3?int = InputMedia;
inputMediaGame#d33f43f3 id:InputGame = InputMedia;
inputMediaInvoice#405fef0d flags:# title:string description:string photo:flags.0?InputWebDocument invoice:Invoice payload:bytes provider:flags.3?string provider_data:DataJSON start_param:flags.1?string extended_media:flags.2?InputMedia = InputMedia;
inputMediaGeoLive#971fa843 flags:# stopped:flags.0?true geo_point:InputGeoPoint heading:flags.2?int period:flags.1?int proximity_notification_radius:flags.3?int = InputMedia;
inputMediaPoll#f94e5f1 flags:# poll:Poll correct_answers:flags.0?Vector<bytes> solution:flags.1?string solution_entities:flags.1?Vector<MessageEntity> = InputMedia;
inputMediaDice#e66fbf7b emoticon:string = InputMedia;
inputMediaStory#89fdd778 peer:InputPeer id:int = InputMedia;
inputMediaWebPage#c21b8849 flags:# force_large_media:flags.0?true force_small_media:flags.1?true optional:flags.2?true url:string = InputMedia;
inputMediaPaidMedia#c4103386 flags:# stars_amount:long extended_media:Vector<InputMedia> payload:flags.0?string = InputMedia;
inputMediaTodo#9fc55fde todo:TodoList = InputMedia;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| inputMediaEmpty | Empty media content of a message. |
| inputMediaUploadedPhoto | Photo |
| inputMediaPhoto | Forwarded photo |
| inputMediaGeoPoint | Map. |
| inputMediaContact | Phone book contact |
| inputMediaUploadedDocument | New document |
| inputMediaDocument | Forwarded document |
| inputMediaVenue | Can be used to send a venue geolocation. |
| inputMediaPhotoExternal | New photo that will be uploaded by the server using the specified URL |
| inputMediaDocumentExternal | Document that will be downloaded by the telegram servers |
| inputMediaGame | A game |
| inputMediaInvoice | Generated invoice of a bot payment |
| inputMediaGeoLive | Live geolocation |
| inputMediaPoll | A poll |
| inputMediaDice | Send a dice-based animated sticker |
| inputMediaStory | Forwarded story |
| inputMediaWebPage | Specifies options that will be used to generate the link preview for the caption, or even a standalone link preview without an attached message. |
| inputMediaPaidMedia | Paid media, see here » for more info. |
| inputMediaTodo | Creates a todo list ». |


## Methods
| Method | Description |
| ---- | ----------- |


