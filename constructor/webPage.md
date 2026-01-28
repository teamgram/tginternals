# webPage
Webpage preview

```
webPage#e89c45b2 flags:# has_large_media:flags.13?true video_cover_photo:flags.14?true id:long url:string display_url:string hash:int type:flags.0?string site_name:flags.1?string title:flags.2?string description:flags.3?string photo:flags.4?Photo embed_url:flags.5?string embed_type:flags.5?string embed_width:flags.6?int embed_height:flags.6?int duration:flags.7?int author:flags.8?string document:flags.9?Document cached_page:flags.10?Page attributes:flags.12?Vector<WebPageAttribute> = WebPage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| has_large_media | flags.13?true | Whether the size of the media in the preview can be changed. |
| video_cover_photo | flags.14?true | Represents a custom video cover. |
| id | long | Preview ID |
| url | string | URL of previewed webpage |
| display_url | string | Webpage URL to be displayed to the user |
| hash | int | Hash used for caching, for more info click here |
| type | flags.0?string | Type of the web page. One of the following: - app- article- document- gif- photo- profile- telegram_album- telegram_background- telegram_bot- telegram_botapp- telegram_call- telegram_channel- telegram_channel_boost- telegram_channel_direct- telegram_channel_request- telegram_chat- telegram_chat_request- telegram_chatlist- telegram_collection- telegram_community- telegram_giftcode- telegram_group_boost- telegram_livestream- telegram_megagroup- telegram_megagroup_request- telegram_message- telegram_nft- telegram_stickerset- telegram_story- telegram_story_album- telegram_theme- telegram_user- telegram_videochat- telegram_voicechat- video |
| site_name | flags.1?string | Short name of the site (e.g., Google Docs, App Store) |
| title | flags.2?string | Title of the content |
| description | flags.3?string | Content description |
| photo | flags.4?Photo | Image representing the content |
| embed_url | flags.5?string | URL to show in the embedded preview |
| embed_type | flags.5?string | MIME type of the embedded preview, (e.g., text/html or video/mp4) |
| embed_width | flags.6?int | Width of the embedded preview |
| embed_height | flags.6?int | Height of the embedded preview |
| duration | flags.7?int | Duration of the content, in seconds |
| author | flags.8?string | Author of the content |
| document | flags.9?Document | Preview of the content as a media file |
| cached_page | flags.10?Page | Page contents in instant view format |
| attributes | flags.12?Vector<WebPageAttribute> | Webpage attributes |


## Type
WebPage

## Related pages
