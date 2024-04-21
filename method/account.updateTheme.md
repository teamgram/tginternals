# account.updateTheme
Update theme

```
theme#a00e67d6 flags:# creator:flags.0?true default:flags.1?true for_chat:flags.5?true id:long access_hash:long slug:string title:string document:flags.2?Document settings:flags.3?Vector<ThemeSettings> emoticon:flags.6?string installs_count:flags.4?int = Theme;
---functions---
account.updateTheme#2bf40ccc flags:# format:string theme:InputTheme slug:flags.0?string title:flags.1?string document:flags.2?InputDocument settings:flags.3?Vector<InputThemeSettings> = Theme;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| format | string | Theme format, a string that identifies the theming engines supported by the client |
| theme | InputTheme | Theme to update |
| slug | flags.0?string | Unique theme ID |
| title | flags.1?string | Theme name |
| document | flags.2?InputDocument | Theme file |
| settings | flags.3?Vector<InputThemeSettings> | Theme settings |


## Result
Theme

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | THEME_INVALID | Invalid theme provided. |

