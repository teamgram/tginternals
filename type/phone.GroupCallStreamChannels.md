# phone.GroupCallStreamChannels
Info about RTMP streams in a group call or livestream

```
phone.groupCallStreamChannels#d0e482b2 channels:Vector<GroupCallStreamChannel> = phone.GroupCallStreamChannels;

---functions---

phone.getGroupCallStreamChannels#1ab21940 call:InputGroupCall = phone.GroupCallStreamChannels;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| phone.groupCallStreamChannels | Info about RTMP streams in a group call or livestream |


## Methods
| Method | Description |
| ---- | ----------- |
| phone.getGroupCallStreamChannels | Get info about RTMP streams in a group call or livestream.  This method should be invoked to the same group/channel-related DC used for downloading livestream chunks.  As usual, the media DC is preferred, if available. |


