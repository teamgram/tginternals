# help.PromoData
Info about pinned MTProxy or Public Service Announcement peers.

```
help.promoDataEmpty#98f6ac75 expires:int = help.PromoData;
help.promoData#8c39793f flags:# proxy:flags.0?true expires:int peer:Peer chats:Vector<Chat> users:Vector<User> psa_type:flags.1?string psa_message:flags.2?string = help.PromoData;

---functions---

help.getPromoData#c0977421 = help.PromoData;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| help.promoDataEmpty | No PSA/MTProxy info is available |
| help.promoData | MTProxy/Public Service Announcement information |


## Methods
| Method | Description |
| ---- | ----------- |
| help.getPromoData | Get MTProxy/Public Service Announcement information |


