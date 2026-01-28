# inputMediaDocumentExternal
Document that will be downloaded by the telegram servers

```
inputMediaDocumentExternal#779600f9 flags:# spoiler:flags.1?true url:string ttl_seconds:flags.0?int video_cover:flags.2?InputPhoto video_timestamp:flags.3?int = InputMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| spoiler | flags.1?true | Whether this media should be hidden behind a spoiler warning |
| url | string | URL of the document |
| ttl_seconds | flags.0?int | Self-destruct time to live of document |
| video_cover | flags.2?InputPhoto | Custom video cover. |
| video_timestamp | flags.3?int | Start playing the video at the specified timestamp (seconds). |


## Type
InputMedia

## Related pages
