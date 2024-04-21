# autoDownloadSettings
Autodownload settings

```
autoDownloadSettings#baa57628 flags:# disabled:flags.0?true video_preload_large:flags.1?true audio_preload_next:flags.2?true phonecalls_less_data:flags.3?true stories_preload:flags.4?true photo_size_max:int video_size_max:long file_size_max:long video_upload_maxbitrate:int small_queue_active_operations_max:int large_queue_active_operations_max:int = AutoDownloadSettings;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| disabled | flags.0?true | Disable automatic media downloads? |
| video_preload_large | flags.1?true | Whether to preload the first seconds of videos larger than the specified limit |
| audio_preload_next | flags.2?true | Whether to preload the next audio track when you're listening to music |
| phonecalls_less_data | flags.3?true | Whether to enable data saving mode in phone calls |
| stories_preload | flags.4?true | Whether to preload stories; in particular, the first documentAttributeVideo.preload_prefix_size bytes of story videos should be preloaded. |
| photo_size_max | int | Maximum size of photos to preload |
| video_size_max | long | Maximum size of videos to preload |
| file_size_max | long | Maximum size of other files to preload |
| video_upload_maxbitrate | int | Maximum suggested bitrate for uploading videos |
| small_queue_active_operations_max | int | A limit, specifying the maximum number of files that should be downloaded in parallel from the same DC, for files smaller than 20MB. |
| large_queue_active_operations_max | int | A limit, specifying the maximum number of files that should be downloaded in parallel from the same DC, for files bigger than 20MB. |


## Type
AutoDownloadSettings

## Related pages
