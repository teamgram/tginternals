# updateBotBusinessConnect
Connecting or disconnecting a business bot or changing the connection settings will emit an updateBotBusinessConnect update to the bot, with the new settings and a connection_id that will be used by the bot to handle updates from and send messages as the user.

```
updateBotBusinessConnect#8ae5c97a connection:BotBusinessConnection qts:int = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| connection | BotBusinessConnection | Business connection settings |
| qts | int | New qts value, see updates » for more info. |


## Type
Update

## Related pages
