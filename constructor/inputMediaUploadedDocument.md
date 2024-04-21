# inputMediaUploadedDocument
New document

```
inputMediaUploadedDocument#5b38c6c1 flags:# nosound_video:flags.3?true force_file:flags.4?true spoiler:flags.5?true file:InputFile thumb:flags.2?InputFile mime_type:string attributes:Vector<DocumentAttribute> stickers:flags.0?Vector<InputDocument> ttl_seconds:flags.1?int = InputMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| nosound_video | flags.3?true | Whether the specified document is a video file with no audio tracks (a GIF animation (even as MPEG4), for example) |
| force_file | flags.4?true | Force the media file to be uploaded as document |
| spoiler | flags.5?true | Whether this media should be hidden behind a spoiler warning |
| file | InputFile | The uploaded file |
| thumb | flags.2?InputFile | Thumbnail of the document, uploaded as for the file |
| mime_type | string | MIME type of document |
| attributes | Vector<DocumentAttribute> | Attributes that specify the type of the document (video, audio, voice, sticker, etc.) |
| stickers | flags.0?Vector<InputDocument> | Attached stickers |
| ttl_seconds | flags.1?int | Time to live in seconds of self-destructing document |


## Type
InputMedia

## Related pages
