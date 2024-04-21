# updateTranscribedAudio
A pending voice message transcription » initiated with messages.transcribeAudio was updated.

```
updateTranscribedAudio#84cd5a flags:# pending:flags.0?true peer:Peer msg_id:int transcription_id:long text:string = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| pending | flags.0?true | Whether this transcription is still pending and further updateTranscribedAudio about it will be sent in the future. |
| peer | Peer | Peer of the transcribed message |
| msg_id | int | Transcribed message ID |
| transcription_id | long | Transcription ID |
| text | string | Transcribed text |


## Type
Update

## Related pages
