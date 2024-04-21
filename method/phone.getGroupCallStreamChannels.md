# phone.getGroupCallStreamChannels
Get info about RTMP streams in a group call or livestream.
This method should be invoked to the same group/channel-related DC used for downloading livestream chunks.
As usual, the media DC is preferred, if available.

```
phone.groupCallStreamChannels#d0e482b2 channels:Vector<GroupCallStreamChannel> = phone.GroupCallStreamChannels;
---functions---
phone.getGroupCallStreamChannels#1ab21940 call:InputGroupCall = phone.GroupCallStreamChannels;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| call | InputGroupCall | Group call or livestream |


## Result
phone.GroupCallStreamChannels

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | GROUPCALL_INVALID | The specified group call is invalid. |
| 400 | GROUPCALL_JOIN_MISSING | You haven't joined this group call. |

