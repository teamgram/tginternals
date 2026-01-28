# bots.checkDownloadFileParams
Check if a mini app can request the download of a specific file: called when handling web_app_request_file_download events »

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
bots.checkDownloadFileParams#50077589 bot:InputUser file_name:string url:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| bot | InputUser | The bot that owns the mini app that requested the download |
| file_name | string | The filename from the web_app_request_file_download event » |
| url | string | The url from the web_app_request_file_download event » |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_INVALID | This is not a valid bot. |

