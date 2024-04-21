# messages.transcribedAudio
Transcribed text from a voice message »

```
messages.transcribedAudio#cfb9d957 flags:# pending:flags.0?true transcription_id:long text:string trial_remains_num:flags.1?int trial_remains_until_date:flags.1?int = messages.TranscribedAudio;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| pending | flags.0?true | Whether the transcription is partial because audio transcription is still in progress, if set the user may receive further updateTranscribedAudio updates with the updated transcription. |
| transcription_id | long | Transcription ID |
| text | string | Transcripted text |
| trial_remains_num | flags.1?int | For non-Premium users, this flag will be set, indicating the remaining transcriptions in the free trial period. |
| trial_remains_until_date | flags.1?int | For non-Premium users, this flag will be set, indicating the date when the trial_remains_num counter will be reset to the maximum value of transcribe_audio_trial_weekly_number. |


## Type
messages.TranscribedAudio

## Related pages
