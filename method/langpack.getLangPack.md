# langpack.getLangPack
Get localization pack strings

```
langPackDifference#f385c1f6 lang_code:string from_version:int version:int strings:Vector<LangPackString> = LangPackDifference;
---functions---
langpack.getLangPack#f2f2330a lang_pack:string lang_code:string = LangPackDifference;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| lang_pack | string | Platform identifier (i.e. android, tdesktop, etc). |
| lang_code | string | Either an ISO 639-1 language code or a language pack name obtained from a language pack link. |


## Result
LangPackDifference

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | LANGUAGE_INVALID | The specified lang_code is invalid. |
| 400 | LANG_CODE_NOT_SUPPORTED | The specified language code is not supported. |
| 400 | LANG_PACK_INVALID | The provided language pack is invalid. |

