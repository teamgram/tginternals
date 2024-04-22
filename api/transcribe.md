# Voice message transcription

The API provides methods to transcribe voice messages.

Schema:

Use messages.transcribeAudio to initiate transcription of a message.
The returned messages.transcribedAudio constructor will have the pending flag set if the transcription is still in progress and the transcribed text contained in text will be updated in future with updateTranscribedAudio updates.
These updates will contain the updated text with the same transcription_id returned in the first messages.transcribedAudio, and the pending flag will be set if the transcription is still in progress.

A transcription can then be rated as good or bad using messages.rateTranscribedAudio.

Users without a Telegram Premium subscription can only transcribe transcribe_audio_trial_weekly_number messages per week, each of maximum duration equal to transcribe_audio_trial_duration_max seconds.
For non-premium users, the trial_remains_num and trial_remains_until_date flags of messages.transcribedAudio will also be set, indicating the remaining transcriptions, and the date when the trial_remains_num counter will be reset to the maximum value of transcribe_audio_trial_weekly_number.

