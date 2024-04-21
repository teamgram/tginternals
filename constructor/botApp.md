# botApp
Contains information about a direct link Mini App.

```
botApp#95fcd1d6 flags:# id:long access_hash:long short_name:string title:string description:string photo:Photo document:flags.0?Document hash:long = BotApp;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| id | long | bot mini app ID |
| access_hash | long | bot mini app access hash |
| short_name | string | bot mini app short name, used to generate Direct Mini App deep links. |
| title | string | bot mini app title. |
| description | string | bot mini app description. |
| photo | Photo | bot mini app photo. |
| document | flags.0?Document | bot mini app animation. |
| hash | long | Hash to pass to messages.getBotApp, to avoid refetching bot app info if it hasn't changed. |


## Type
BotApp

## Related pages
