# account.getTheme
Get theme information

```
theme#a00e67d6 flags:# creator:flags.0?true default:flags.1?true for_chat:flags.5?true id:long access_hash:long slug:string title:string document:flags.2?Document settings:flags.3?Vector<ThemeSettings> emoticon:flags.6?string installs_count:flags.4?int = Theme;
---functions---
account.getTheme#3a5869ec format:string theme:InputTheme = Theme;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| format | string | Theme format, a string that identifies the theming engines supported by the client |
| theme | InputTheme | Theme |


## Result
Theme

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | THEME_FORMAT_INVALID | Invalid theme format provided. |
| 400 | THEME_INVALID | Invalid theme provided. |

