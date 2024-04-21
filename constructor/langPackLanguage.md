# langPackLanguage
Identifies a localization pack

```
langPackLanguage#eeca5ce3 flags:# official:flags.0?true rtl:flags.2?true beta:flags.3?true name:string native_name:string lang_code:string base_lang_code:flags.1?string plural_code:string strings_count:int translated_count:int translations_url:string = LangPackLanguage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| official | flags.0?true | Whether the language pack is official |
| rtl | flags.2?true | Is this a localization pack for an RTL language |
| beta | flags.3?true | Is this a beta localization pack? |
| name | string | Language name |
| native_name | string | Language name in the language itself |
| lang_code | string | Language code (pack identifier) |
| base_lang_code | flags.1?string | Identifier of a base language pack; may be empty. If a string is missed in the language pack, then it should be fetched from base language pack. Unsupported in custom language packs |
| plural_code | string | A language code to be used to apply plural forms. See https://www.unicode.org/cldr/charts/latest/supplemental/language_plural_rules.html for more info |
| strings_count | int | Total number of non-deleted strings from the language pack |
| translated_count | int | Total number of translated strings from the language pack |
| translations_url | string | Link to language translation interface; empty for custom local language packs |


## Type
LangPackLanguage

## Related pages
