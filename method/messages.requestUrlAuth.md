# messages.requestUrlAuth
Get more info about a Seamless Telegram Login authorization request, for more info click here »

```
urlAuthResultRequest#92d33a0e flags:# request_write_access:flags.0?true bot:User domain:string = UrlAuthResult;
urlAuthResultAccepted#8f8c0e4e url:string = UrlAuthResult;
urlAuthResultDefault#a9d6db1f = UrlAuthResult;
---functions---
messages.requestUrlAuth#198fb446 flags:# peer:flags.1?InputPeer msg_id:flags.1?int button_id:flags.1?int url:flags.2?string = UrlAuthResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | flags.1?InputPeer | Peer where the message is located |
| msg_id | flags.1?int | The message |
| button_id | flags.1?int | The ID of the button with the authorization request |
| url | flags.2?string | URL used for link URL authorization, click here for more info » |


## Result
UrlAuthResult

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

