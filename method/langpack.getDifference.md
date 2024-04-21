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
| lang_pack | string | Language pack |
| lang_code | string | Language code |
| from_version | int | Previous localization pack version |


## Result
LangPackDifference

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | LANG_PACK_INVALID | The provided language pack is invalid. |

