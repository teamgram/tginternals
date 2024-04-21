# messageMediaWebPage
Preview of webpage

```
messageMediaWebPage#ddf10c3b flags:# force_large_media:flags.0?true force_small_media:flags.1?true manual:flags.3?true safe:flags.4?true webpage:WebPage = MessageMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| force_large_media | flags.0?true | If set, specifies that a large media preview should be used. |
| force_small_media | flags.1?true | If set, specifies that a small media preview should be used. |
| manual | flags.3?true | If set, indicates that the URL used for the webpage preview was specified manually using inputMediaWebPage, and may not be related to any of the URLs specified in the message. |
| safe | flags.4?true | If set, the webpage can be opened directly without user confirmation; otherwise, user confirmation is required, showing the exact URL that will be opened. |
| webpage | WebPage | Webpage preview |


## Type
MessageMedia

## Related pages
