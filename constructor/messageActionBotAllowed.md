# messageActionBotAllowed
We have given the bot permission to send us direct messages.

```
messageActionBotAllowed#c516d679 flags:# attach_menu:flags.1?true from_request:flags.3?true domain:flags.0?string app:flags.2?BotApp = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| attach_menu | flags.1?true | We have authorized the bot to send us messages by installing the bot's attachment menu. |
| from_request | flags.3?true | We have allowed the bot to send us messages using bots.allowSendMessage ». |
| domain | flags.0?string | We have authorized the bot to send us messages by logging into a website via Telegram Login »; this field contains the domain name of the website on which the user has logged in. |
| app | flags.2?BotApp | We have authorized the bot to send us messages by opening the specified bot mini app. |


## Type


## Related pages
