# langpack.getDifference
Get new strings in language pack

```
langPackDifference#f385c1f6 lang_code:string from_version:int version:int strings:Vector<LangPackString> = LangPackDifference;
---functions---
langpack.getDifference#cd984aa5 lang_pack:string lang_code:string from_version:int = LangPackDifference;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| lang_pack | string | Platform identifier (i.e. android, tdesktop, etc). |
| lang_code | string | Either an ISO 639-1 language code or a language pack name obtained from a language pack link. |
| from_version | int | Previous localization pack version |


## Result
LangPackDifference

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | LANG_PACK_INVALID | The provided language pack is invalid. |

