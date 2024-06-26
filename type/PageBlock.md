# PageBlock
Represents an instant view page element

```
pageBlockUnsupported#13567e8a = PageBlock;
pageBlockTitle#70abc3fd text:RichText = PageBlock;
pageBlockSubtitle#8ffa9a1f text:RichText = PageBlock;
pageBlockAuthorDate#baafe5e0 author:RichText published_date:int = PageBlock;
pageBlockHeader#bfd064ec text:RichText = PageBlock;
pageBlockSubheader#f12bb6e1 text:RichText = PageBlock;
pageBlockParagraph#467a0766 text:RichText = PageBlock;
pageBlockPreformatted#c070d93e text:RichText language:string = PageBlock;
pageBlockFooter#48870999 text:RichText = PageBlock;
pageBlockDivider#db20b188 = PageBlock;
pageBlockAnchor#ce0d37b0 name:string = PageBlock;
pageBlockList#e4e88011 items:Vector<PageListItem> = PageBlock;
pageBlockBlockquote#263d7c26 text:RichText caption:RichText = PageBlock;
pageBlockPullquote#4f4456d3 text:RichText caption:RichText = PageBlock;
pageBlockPhoto#1759c560 flags:# photo_id:long caption:PageCaption url:flags.0?string webpage_id:flags.0?long = PageBlock;
pageBlockVideo#7c8fe7b6 flags:# autoplay:flags.0?true loop:flags.1?true video_id:long caption:PageCaption = PageBlock;
pageBlockCover#39f23300 cover:PageBlock = PageBlock;
pageBlockEmbed#a8718dc5 flags:# full_width:flags.0?true allow_scrolling:flags.3?true url:flags.1?string html:flags.2?string poster_photo_id:flags.4?long w:flags.5?int h:flags.5?int caption:PageCaption = PageBlock;
pageBlockEmbedPost#f259a80b url:string webpage_id:long author_photo_id:long author:string date:int blocks:Vector<PageBlock> caption:PageCaption = PageBlock;
pageBlockCollage#65a0fa4d items:Vector<PageBlock> caption:PageCaption = PageBlock;
pageBlockSlideshow#31f9590 items:Vector<PageBlock> caption:PageCaption = PageBlock;
pageBlockChannel#ef1751b5 channel:Chat = PageBlock;
pageBlockAudio#804361ea audio_id:long caption:PageCaption = PageBlock;
pageBlockKicker#1e148390 text:RichText = PageBlock;
pageBlockTable#bf4dea82 flags:# bordered:flags.0?true striped:flags.1?true title:RichText rows:Vector<PageTableRow> = PageBlock;
pageBlockOrderedList#9a8ae1e1 items:Vector<PageListOrderedItem> = PageBlock;
pageBlockDetails#76768bed flags:# open:flags.0?true blocks:Vector<PageBlock> title:RichText = PageBlock;
pageBlockRelatedArticles#16115a96 title:RichText articles:Vector<PageRelatedArticle> = PageBlock;
pageBlockMap#a44f3ef6 geo:GeoPoint zoom:int w:int h:int caption:PageCaption = PageBlock;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| pageBlockUnsupported | Unsupported IV element |
| pageBlockTitle | Title |
| pageBlockSubtitle | Subtitle |
| pageBlockAuthorDate | Author and date of creation of article |
| pageBlockHeader | Page header |
| pageBlockSubheader | Subheader |
| pageBlockParagraph | A paragraph |
| pageBlockPreformatted | Preformatted (<pre> text) |
| pageBlockFooter | Page footer |
| pageBlockDivider | An empty block separating a page |
| pageBlockAnchor | Link to section within the page itself (like <a href="#target">anchor</a>) |
| pageBlockList | Unordered list of IV blocks |
| pageBlockBlockquote | Quote (equivalent to the HTML <blockquote>) |
| pageBlockPullquote | Pullquote |
| pageBlockPhoto | A photo |
| pageBlockVideo | Video |
| pageBlockCover | A page cover |
| pageBlockEmbed | An embedded webpage |
| pageBlockEmbedPost | An embedded post |
| pageBlockCollage | Collage of media |
| pageBlockSlideshow | Slideshow |
| pageBlockChannel | Reference to a telegram channel |
| pageBlockAudio | Audio |
| pageBlockKicker | Kicker |
| pageBlockTable | Table |
| pageBlockOrderedList | Ordered list of IV blocks |
| pageBlockDetails | A collapsible details block |
| pageBlockRelatedArticles | Related articles |
| pageBlockMap | A map |


## Methods
| Method | Description |
| ---- | ----------- |


