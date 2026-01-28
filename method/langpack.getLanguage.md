# langpack.getLanguage
Get information about a language in a localization pack

```
langPackLanguage#eeca5ce3 flags:# official:flags.0?true rtl:flags.2?true beta:flags.3?true name:string native_name:string lang_code:string base_lang_code:flags.1?string plural_code:string strings_count:int translated_count:int translations_url:string = LangPackLanguage;
---functions---
langpack.getLanguage#6a596502 lang_pack:string lang_code:string = LangPackLanguage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| lang_pack | string | Platform identifier (i.e. android, tdesktop, etc). |
| lang_code | string | Either an ISO 639-1 language code or a language pack name obtained from a language pack link. |


## Result
LangPackLanguage

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | LANG_CODE_NOT_SUPPORTED | The specified language code is not supported. |
| 400 | LANG_PACK_INVALID | The provided language pack is invalid. |

