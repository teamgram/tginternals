# UrlAuthResult
URL authorization result

```
urlAuthResultRequest#92d33a0e flags:# request_write_access:flags.0?true bot:User domain:string = UrlAuthResult;
urlAuthResultAccepted#8f8c0e4e url:string = UrlAuthResult;
urlAuthResultDefault#a9d6db1f = UrlAuthResult;

---functions---

messages.requestUrlAuth#198fb446 flags:# peer:flags.1?InputPeer msg_id:flags.1?int button_id:flags.1?int url:flags.2?string = UrlAuthResult;
messages.acceptUrlAuth#b12c7125 flags:# write_allowed:flags.0?true peer:flags.1?InputPeer msg_id:flags.1?int button_id:flags.1?int url:flags.2?string = UrlAuthResult;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| urlAuthResultRequest | Details about the authorization request, for more info click here » |
| urlAuthResultAccepted | Details about an accepted authorization request, for more info click here » |
| urlAuthResultDefault | Details about an accepted authorization request, for more info click here » |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.requestUrlAuth | Get more info about a Seamless Telegram Login authorization request, for more info click here » |
| messages.acceptUrlAuth | Use this to accept a Seamless Telegram Login authorization request, for more info click here » |


