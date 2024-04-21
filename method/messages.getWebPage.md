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
| hash | int | Hash for pagination, for more info click here |


## Result
messages.WebPage

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | WC_CONVERT_URL_INVALID | WC convert URL invalid. |

