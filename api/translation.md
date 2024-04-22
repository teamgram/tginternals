# Translation
Telegram allows translating chat messages: Telegram Premium users may even enable real-time chat translation.
messages.translateText can be used to translate a list of chat messages (by populating the peer and id flags), or a generic list of messages (by populating the text flag, for example when translating instant view articles).
The method will return a vector of textWithEntities constructors, containing the translated text, and, only for Telegram Premium users, the corresponding styled text entities (i.e. correctly repositioned bold, italic, link entities for the translated message, corresponding to the same entities in the original message).
### Real-time translation
Telegram Premium users may also enable real-time chat translation.
If the currently logged in account is a Premium account, and the translations_disabled flag of userFull, chatFull, channelFull is not set, the client should run a local language recognition model for all messages received from private chats (not secret chats), chats and channels, and if:
- The language recognition model was ran on at least 8 messages in the chat,
- and the language of at least 35% of the processed messages was successfully detected,
- and at least 65% of the messages whose language was successfully detected are in a foreign language (a language that is not the system language nor the Telegram in-app language, and a language that was not explicitly excluded from translation by the user),
- then, a popup should be displayed to the user, offering to enable real-time chat translation, or to disallow translation of the detected language (the detected language is the language with most occurrences amongst all processed messages).
If the user dismisses the autotranslation popup, invoke messages.togglePeerTranslations with the disabled flag set: this will set the translations_disabled flag in the corresponding full info constructor, signaling to the other sessions that the autotranslation popup should not be displayed.
If the user enables autotranslation, store the preference locally and invoke messages.translateText for every received message, preferrably batching requests by specifying multiple message IDs in id.
