# phone.GroupCallStreamRtmpUrl
RTMP URL and stream key to be used in streaming software

```
phone.groupCallStreamRtmpUrl#2dbf3432 url:string key:string = phone.GroupCallStreamRtmpUrl;

---functions---

phone.getGroupCallStreamRtmpUrl#deb3abbf peer:InputPeer revoke:Bool = phone.GroupCallStreamRtmpUrl;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| phone.groupCallStreamRtmpUrl | RTMP URL and stream key to be used in streaming software |


## Methods
| Method | Description |
| ---- | ----------- |
| phone.getGroupCallStreamRtmpUrl | Get RTMP URL and stream key for RTMP livestreams. Can be used even before creating the actual RTMP livestream with phone.createGroupCall (the rtmp_stream flag must be set). |


