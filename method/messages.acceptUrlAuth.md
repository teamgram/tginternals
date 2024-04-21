# messages.acceptUrlAuth
Use this to accept a Seamless Telegram Login authorization request, for more info click here »

```
urlAuthResultRequest#92d33a0e flags:# request_write_access:flags.0?true bot:User domain:string = UrlAuthResult;
urlAuthResultAccepted#8f8c0e4e url:string = UrlAuthResult;
urlAuthResultDefault#a9d6db1f = UrlAuthResult;
---functions---
messages.acceptUrlAuth#b12c7125 flags:# write_allowed:flags.0?true peer:flags.1?InputPeer msg_id:flags.1?int button_id:flags.1?int url:flags.2?string = UrlAuthResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| write_allowed | flags.0?true | Set this flag to allow the bot to send messages to you (if requested) |
| peer | flags.1?InputPeer | The location of the message |
| msg_id | flags.1?int | Message ID of the message with the login button |
| button_id | flags.1?int | ID of the login button |
| url | flags.2?string | URL used for link URL authorization, click here for more info » |


## Result
UrlAuthResult

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

