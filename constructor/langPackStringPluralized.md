# langPackStringPluralized
A language pack string which has different forms based on the number of some object it mentions. See https://www.unicode.org/cldr/charts/latest/supplemental/language_plural_rules.html for more info

```
langPackStringPluralized#6c47ac9f flags:# key:string zero_value:flags.0?string one_value:flags.1?string two_value:flags.2?string few_value:flags.3?string many_value:flags.4?string other_value:string = LangPackString;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| key | string | Localization key |
| zero_value | flags.0?string | Value for zero objects |
| one_value | flags.1?string | Value for one object |
| two_value | flags.2?string | Value for two objects |
| few_value | flags.3?string | Value for a few objects |
| many_value | flags.4?string | Value for many objects |
| other_value | string | Default value |


## Type
LangPackString

## Related pages
