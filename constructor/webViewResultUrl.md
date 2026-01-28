# webViewResultUrl
Contains the webview URL with appropriate theme and user info parameters added

```
webViewResultUrl#4d22ff98 flags:# fullsize:flags.1?true fullscreen:flags.2?true query_id:flags.0?long url:string = WebViewResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| fullsize | flags.1?true | If set, the app must be opened in fullsize mode instead of compact mode. |
| fullscreen | flags.2?true | If set, the app must be opened in fullscreen |
| query_id | flags.0?long | Webview session ID (only returned by inline button mini apps, menu button mini apps, attachment menu mini apps). |
| url | string | Webview URL to open |


## Type
WebViewResult

## Related pages
