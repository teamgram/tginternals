# page
Instant view page

```
page#98657f0d flags:# part:flags.0?true rtl:flags.1?true v2:flags.2?true url:string blocks:Vector<PageBlock> photos:Vector<Photo> documents:Vector<Document> views:flags.3?int = Page;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| part | flags.0?true | Indicates that not full page preview is available to the client and it will need to fetch full Instant View from the server using messages.getWebPagePreview. |
| rtl | flags.1?true | Whether the page contains RTL text |
| v2 | flags.2?true | Whether this is an IV v2 page |
| url | string | Original page HTTP URL |
| blocks | Vector<PageBlock> | Page elements (like with HTML elements, only as TL constructors) |
| photos | Vector<Photo> | Photos in page |
| documents | Vector<Document> | Media in page |
| views | flags.3?int | View count |


## Type
Page

## Related pages
