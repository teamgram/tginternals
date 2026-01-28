# messages.getWebPage
Get instant view page

```
messages.webPage#fd5e12bd webpage:WebPage chats:Vector<Chat> users:Vector<User> = messages.WebPage;
---functions---
messages.getWebPage#8d9692a3 url:string hash:int = messages.WebPage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| url | string | URL of IV page to fetch |
| hash | int | Hash used for caching, for more info click here. Note: the usual hash generation algorithm cannot be used in this case, please re-use the webPage.hash field returned by a previous call to the method, or pass 0 if this is the first call or if the previous call did not return a webPage. |


## Result
messages.WebPage

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | WC_CONVERT_URL_INVALID | WC convert URL invalid. |

