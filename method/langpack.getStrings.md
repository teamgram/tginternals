# langpack.getStrings
Get strings from a language pack

```
---functions---
langpack.getStrings#efea3803 lang_pack:string lang_code:string keys:Vector<string> = Vector<LangPackString>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| lang_pack | string | Platform identifier (i.e. android, tdesktop, etc). |
| lang_code | string | Either an ISO 639-1 language code or a language pack name obtained from a language pack link. |
| keys | Vector<string> | Strings to get |


## Result
Vector<LangPackString>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | LANG_CODE_NOT_SUPPORTED | The specified language code is not supported. |
| 400 | LANG_PACK_INVALID | The provided language pack is invalid. |

