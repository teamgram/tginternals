# payments.getStarsRevenueAdsAccountUrl
Returns a URL for a Telegram Ad platform account that can be used to set up advertisements for channel/bot in peer, paid using the Telegram Stars owned by the specified peer, see here » for more info.

```
payments.starsRevenueAdsAccountUrl#394e7f21 url:string = payments.StarsRevenueAdsAccountUrl;
---functions---
payments.getStarsRevenueAdsAccountUrl#d1d7efc5 peer:InputPeer = payments.StarsRevenueAdsAccountUrl;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Channel or bot that owns the stars. |


## Result
payments.StarsRevenueAdsAccountUrl

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

