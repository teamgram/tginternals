# WebPage
Instant View webpage preview

```
webPageEmpty#211a1788 flags:# id:long url:flags.0?string = WebPage;
webPagePending#b0d13e47 flags:# id:long url:flags.0?string date:int = WebPage;
webPage#e89c45b2 flags:# has_large_media:flags.13?true id:long url:string display_url:string hash:int type:flags.0?string site_name:flags.1?string title:flags.2?string description:flags.3?string photo:flags.4?Photo embed_url:flags.5?string embed_type:flags.5?string embed_width:flags.6?int embed_height:flags.6?int duration:flags.7?int author:flags.8?string document:flags.9?Document cached_page:flags.10?Page attributes:flags.12?Vector<WebPageAttribute> = WebPage;
webPageNotModified#7311ca11 flags:# cached_page_views:flags.0?int = WebPage;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| webPageEmpty | No preview is available for the webpage |
| webPagePending | A preview of the webpage is currently being generated |
| webPage | Webpage preview |
| webPageNotModified | The preview of the webpage hasn't changed |


## Methods
| Method | Description |
| ---- | ----------- |


