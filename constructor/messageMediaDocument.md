# messageMediaDocument
Document (video, audio, voice, sticker, any media type except photo)

```
messageMediaDocument#52d8ccd9 flags:# nopremium:flags.3?true spoiler:flags.4?true video:flags.6?true round:flags.7?true voice:flags.8?true document:flags.0?Document alt_documents:flags.5?Vector<Document> video_cover:flags.9?Photo video_timestamp:flags.10?int ttl_seconds:flags.2?int = MessageMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| nopremium | flags.3?true | Whether this is a normal sticker, if not set this is a premium sticker and a premium sticker animation must be played. |
| spoiler | flags.4?true | Whether this media should be hidden behind a spoiler warning |
| video | flags.6?true | Whether this is a video. |
| round | flags.7?true | Whether this is a round video. |
| voice | flags.8?true | Whether this is a voice message. |
| document | flags.0?Document | Attached document |
| alt_documents | flags.5?Vector<Document> | Videos only, contains alternative qualities of the video. |
| video_cover | flags.9?Photo | Custom video cover. |
| video_timestamp | flags.10?int | Start playing the video at the specified timestamp (seconds). |
| ttl_seconds | flags.2?int | Time to live of self-destructing document |


## Type
MessageMedia

## Related pages
