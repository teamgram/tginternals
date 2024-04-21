# SendMessageAction
User actions. Use this to provide users with detailed info about their chat partner's actions: typing or sending attachments of all kinds.

```
sendMessageTypingAction#16bf744e = SendMessageAction;
sendMessageCancelAction#fd5ec8f5 = SendMessageAction;
sendMessageRecordVideoAction#a187d66f = SendMessageAction;
sendMessageUploadVideoAction#e9763aec progress:int = SendMessageAction;
sendMessageRecordAudioAction#d52f73f7 = SendMessageAction;
sendMessageUploadAudioAction#f351d7ab progress:int = SendMessageAction;
sendMessageUploadPhotoAction#d1d34a26 progress:int = SendMessageAction;
sendMessageUploadDocumentAction#aa0cd9e4 progress:int = SendMessageAction;
sendMessageGeoLocationAction#176f8ba1 = SendMessageAction;
sendMessageChooseContactAction#628cbc6f = SendMessageAction;
sendMessageGamePlayAction#dd6a8f48 = SendMessageAction;
sendMessageRecordRoundAction#88f27fbc = SendMessageAction;
sendMessageUploadRoundAction#243e1c66 progress:int = SendMessageAction;
speakingInGroupCallAction#d92c2285 = SendMessageAction;
sendMessageHistoryImportAction#dbda9246 progress:int = SendMessageAction;
sendMessageChooseStickerAction#b05ac6b1 = SendMessageAction;
sendMessageEmojiInteraction#25972bcb emoticon:string msg_id:int interaction:DataJSON = SendMessageAction;
sendMessageEmojiInteractionSeen#b665902e emoticon:string = SendMessageAction;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| sendMessageTypingAction | User is typing. |
| sendMessageCancelAction | Invalidate all previous action updates. E.g. when user deletes entered text or aborts a video upload. |
| sendMessageRecordVideoAction | User is recording a video. |
| sendMessageUploadVideoAction | User is uploading a video. |
| sendMessageRecordAudioAction | User is recording a voice message. |
| sendMessageUploadAudioAction | User is uploading a voice message. |
| sendMessageUploadPhotoAction | User is uploading a photo. |
| sendMessageUploadDocumentAction | User is uploading a file. |
| sendMessageGeoLocationAction | User is selecting a location to share. |
| sendMessageChooseContactAction | User is selecting a contact to share. |
| sendMessageGamePlayAction | User is playing a game |
| sendMessageRecordRoundAction | User is recording a round video to share |
| sendMessageUploadRoundAction | User is uploading a round video |
| speakingInGroupCallAction | User is currently speaking in the group call |
| sendMessageHistoryImportAction | Chat history is being imported |
| sendMessageChooseStickerAction | User is choosing a sticker |
| sendMessageEmojiInteraction | User has clicked on an animated emoji triggering a reaction, click here for more info ». |
| sendMessageEmojiInteractionSeen | User is watching an animated emoji reaction triggered by another user, click here for more info ». |


## Methods
| Method | Description |
| ---- | ----------- |


