# account.installTheme
Install a theme

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.installTheme#c727bb3b flags:# dark:flags.0?true theme:flags.1?InputTheme format:flags.2?string base_theme:flags.3?BaseTheme = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| dark | flags.0?true | Whether to install the dark version |
| theme | flags.1?InputTheme | Theme to install |
| format | flags.2?string | Theme format, a string that identifies the theming engines supported by the client |
| base_theme | flags.3?BaseTheme | Indicates a basic theme provided by all clients |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

