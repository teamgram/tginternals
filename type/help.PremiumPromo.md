# help.PremiumPromo
Telegram Premium promotion information

```
help.premiumPromo#5334759c status_text:string status_entities:Vector<MessageEntity> video_sections:Vector<string> videos:Vector<Document> period_options:Vector<PremiumSubscriptionOption> users:Vector<User> = help.PremiumPromo;

---functions---

help.getPremiumPromo#b81b93d4 = help.PremiumPromo;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| help.premiumPromo | Telegram Premium promotion informationNote that the video_sections+videos fields are a list of videos, and the corresponding premium feature identifiers.  They're equivalent to a section => video dictionary, with keys from video_section and values from videos.  The keys in video_sections correspond to a specific feature identifier, and the associated promotional video should be shown when the associated feature row is clicked. |


## Methods
| Method | Description |
| ---- | ----------- |
| help.getPremiumPromo | Get Telegram Premium promotion information |


