# messages.translateText
Translate a given text.

```
messages.translateResult#33db32f8 result:Vector<TextWithEntities> = messages.TranslatedText;
---functions---
messages.translateText#63183030 flags:# peer:flags.0?InputPeer id:flags.0?Vector<int> text:flags.1?Vector<TextWithEntities> to_lang:string = messages.TranslatedText;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | flags.0?InputPeer | If the text is a chat message, the peer ID |
| id | flags.0?Vector<int> | A list of message IDs to translate |
| text | flags.1?Vector<TextWithEntities> | A list of styled messages to translate |
| to_lang | string | Two-letter ISO 639-1 language code of the language to which the message is translated |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | INPUT_TEXT_EMPTY | The specified text is empty. |
| 400 | INPUT_TEXT_TOO_LONG | The specified text is too long. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | TO_LANG_INVALID | The specified destination language is invalid. |
| 500 | TRANSLATE_REQ_FAILED | Translation failed, please try again later. |
| 400 | TRANSLATE_REQ_QUOTA_EXCEEDED | Translation is currently unavailable due to a temporary server-side lack of resources. |
| 406 | TRANSLATIONS_DISABLED | Translations are unavailable, a detailed and localized description for the error will be emitted via an updateServiceNotification as specified here ». |
| 500 | TRANSLATION_TIMEOUT | A timeout occurred while translating the specified text. |

