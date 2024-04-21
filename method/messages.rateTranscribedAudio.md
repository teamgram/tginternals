# messages.rateTranscribedAudio
Rate transcribed voice message

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.rateTranscribedAudio#7f1d072f peer:InputPeer msg_id:int transcription_id:long good:Bool = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer where the voice message was sent |
| msg_id | int | Message ID |
| transcription_id | long | Transcription ID |
| good | Bool | Whether the transcription was correct |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

