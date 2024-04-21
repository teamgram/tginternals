# inputWebFileAudioAlbumThumbLocation
Used to download an album cover for any music file using upload.getWebFile, see the webfile docs for more info ».

```
inputWebFileAudioAlbumThumbLocation#f46fe924 flags:# small:flags.2?true document:flags.0?InputDocument title:flags.1?string performer:flags.1?string = InputWebFileLocation;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| small | flags.2?true | Used to return a thumbnail with 100x100 resolution (instead of the default 600x600) |
| document | flags.0?InputDocument | The audio file in question: must NOT be provided in secret chats, provide the title and performer fields instead. |
| title | flags.1?string | Song title: should only be used in secret chats, in normal chats provide document instead, as it has more lax rate limits. |
| performer | flags.1?string | Song performer: should only be used in secret chats, in normal chats provide document instead, as it has more lax rate limits. |


## Type
InputWebFileLocation

## Related pages
