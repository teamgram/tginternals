# Message drafts
Message drafts in Telegram allow syncing the text typed into message fields between devices.
### Drafts
Drafts are represented by the DraftMessage constructors.
The parameters of the peer-specific draft should be used as defaults when composing a message to be sent to a certain peer (in the case of media, the same draft should still be used as base, the message will become the caption).
If the user exits the app before sending the message, the message should be saved as a draft:
### Saving drafts
Drafts can be saved using the messages.saveDraft method.
### Downloading drafts
New drafts are automatically sent to all devices via updateDraftMessage updates.
Dialog objects fetched via the API also contain the draft associated with the dialog.
### Clearing drafts
Drafts can be cleared by setting the clear_draft flag when sending messages or media using messages.sendMessage, messages.sendMedia, messages.sendMultiMedia, messages.sendInlineBotResult and similar or manually by passing empty values to messages.saveDraft.
