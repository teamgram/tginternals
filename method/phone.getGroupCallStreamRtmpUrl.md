# phone.getGroupCallStreamRtmpUrl
Get RTMP URL and stream key for RTMP livestreams. Can be used even before creating the actual RTMP livestream with phone.createGroupCall (the rtmp_stream flag must be set).

```
phone.groupCallStreamRtmpUrl#2dbf3432 url:string key:string = phone.GroupCallStreamRtmpUrl;
---functions---
phone.getGroupCallStreamRtmpUrl#deb3abbf peer:InputPeer revoke:Bool = phone.GroupCallStreamRtmpUrl;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer to livestream into |
| revoke | Bool | Whether to revoke the previous stream key or simply return the existing one |


## Result
phone.GroupCallStreamRtmpUrl

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |

