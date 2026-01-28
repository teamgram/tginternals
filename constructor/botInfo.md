# botInfo
Info about bots (available bot commands, etc)

```
botInfo#4d8a0299 flags:# has_preview_medias:flags.6?true user_id:flags.0?long description:flags.1?string description_photo:flags.4?Photo description_document:flags.5?Document commands:flags.2?Vector<BotCommand> menu_button:flags.3?BotMenuButton privacy_policy_url:flags.7?string app_settings:flags.8?BotAppSettings verifier_settings:flags.9?BotVerifierSettings = BotInfo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| has_preview_medias | flags.6?true | If set, the bot has some preview medias for the configured Main Mini App, see here » for more info on Main Mini App preview medias. |
| user_id | flags.0?long | ID of the bot |
| description | flags.1?string | Description of the bot |
| description_photo | flags.4?Photo | Description photo |
| description_document | flags.5?Document | Description animation in MPEG4 format |
| commands | flags.2?Vector<BotCommand> | Bot commands that can be used in the chat |
| menu_button | flags.3?BotMenuButton | Indicates the action to execute when pressing the in-UI menu button for bots |
| privacy_policy_url | flags.7?string | The HTTP link to the privacy policy of the bot. If not set, then the /privacy command must be used, if supported by the bot (i.e. if it's present in the commands vector). If it isn't supported, then https://telegram.org/privacy-tpa must be opened, instead. |
| app_settings | flags.8?BotAppSettings | Mini app » settings |
| verifier_settings | flags.9?BotVerifierSettings | This bot can verify peers: this field contains more info about the verification the bot can assign to peers. |


## Type
BotInfo

## Related pages
