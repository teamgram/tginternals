# help.country
Name, ISO code, localized name and phone codes/patterns of a specific country

```
help.country#c3878e23 flags:# hidden:flags.0?true iso2:string default_name:string name:flags.1?string country_codes:Vector<help.CountryCode> = help.Country;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| hidden | flags.0?true | Whether this country should not be shown in the list |
| iso2 | string | ISO code of country |
| default_name | string | Name of the country in the country's language |
| name | flags.1?string | Name of the country in the user's language, if different from the original name |
| country_codes | Vector<help.CountryCode> | Phone codes/patterns |


## Type
help.Country

## Related pages
