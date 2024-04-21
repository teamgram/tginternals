# botInfo
Info about bots (available bot commands, etc)

```
botInfo#8f300b57 flags:# user_id:flags.0?long description:flags.1?string description_photo:flags.4?Photo description_document:flags.5?Document commands:flags.2?Vector<BotCommand> menu_button:flags.3?BotMenuButton = BotInfo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| user_id | flags.0?long | ID of the bot |
| description | flags.1?string | Description of the bot |
| description_photo | flags.4?Photo | Description photo |
| description_document | flags.5?Document | Description animation in MPEG4 format |
| commands | flags.2?Vector<BotCommand> | Bot commands that can be used in the chat |
| menu_button | flags.3?BotMenuButton | Indicates the action to execute when pressing the in-UI menu button for bots |


## Type
BotInfo

## Related pages
