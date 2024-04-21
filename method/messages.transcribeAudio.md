# messages.transcribeAudio
Transcribe voice message

```
messages.transcribedAudio#cfb9d957 flags:# pending:flags.0?true transcription_id:long text:string trial_remains_num:flags.1?int trial_remains_until_date:flags.1?int = messages.TranscribedAudio;
---functions---
messages.transcribeAudio#269e9a49 peer:InputPeer msg_id:int = messages.TranscribedAudio;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer ID where the voice message was sent |
| msg_id | int | Voice message ID |


## Result
messages.TranscribedAudio

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 403 | PREMIUM_ACCOUNT_REQUIRED | A premium account is required to execute this action. |
| 400 | TRANSCRIPTION_FAILED | Audio transcription failed. |

