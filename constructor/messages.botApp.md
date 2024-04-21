# messages.botApp
Contains information about a direct link Mini App

```
messages.botApp#eb50adf5 flags:# inactive:flags.0?true request_write_access:flags.1?true has_settings:flags.2?true app:BotApp = messages.BotApp;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| inactive | flags.0?true | Whether the web app was never used by the user, and confirmation must be asked from the user before opening it. |
| request_write_access | flags.1?true | The bot is asking permission to send messages to the user: if the user agrees, set the write_allowed flag when invoking messages.requestAppWebView. |
| has_settings | flags.2?true | Deprecated flag, can be ignored. |
| app | BotApp | Bot app information |


## Type
messages.BotApp

## Related pages
