# account.createTheme
Create a theme

```
theme#a00e67d6 flags:# creator:flags.0?true default:flags.1?true for_chat:flags.5?true id:long access_hash:long slug:string title:string document:flags.2?Document settings:flags.3?Vector<ThemeSettings> emoticon:flags.6?string installs_count:flags.4?int = Theme;
---functions---
account.createTheme#652e4400 flags:# slug:string title:string document:flags.2?InputDocument settings:flags.3?Vector<InputThemeSettings> = Theme;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| slug | string | Unique theme ID used to generate theme deep links, can be empty to autogenerate a random ID. |
| title | string | Theme name |
| document | flags.2?InputDocument | Theme file |
| settings | flags.3?Vector<InputThemeSettings> | Theme settings, multiple values can be provided for the different base themes (day/night mode, etc). |


## Result
Theme

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | THEME_MIME_INVALID | The theme's MIME type is invalid. |
| 400 | THEME_TITLE_INVALID | The specified theme title is invalid. |

