# channelForbidden
Indicates a channel/supergroup we can't access because we were banned, or for some other reason.

```
channelForbidden#17d493d5 flags:# broadcast:flags.5?true megagroup:flags.8?true id:long access_hash:long title:string until_date:flags.16?int = Chat;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| broadcast | flags.5?true | Is this a channel |
| megagroup | flags.8?true | Is this a supergroup |
| id | long | Channel ID |
| access_hash | long | Access hash |
| title | string | Title |
| until_date | flags.16?int | The ban is valid until the specified date |


## Type
Chat

## Related pages
