# attachMenuBot
Represents a bot mini app that can be launched from the attachment/side menu »

```
attachMenuBot#d90d8dfe flags:# inactive:flags.0?true has_settings:flags.1?true request_write_access:flags.2?true show_in_attach_menu:flags.3?true show_in_side_menu:flags.4?true side_menu_disclaimer_needed:flags.5?true bot_id:long short_name:string peer_types:flags.3?Vector<AttachMenuPeerType> icons:Vector<AttachMenuBotIcon> = AttachMenuBot;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| inactive | flags.0?true | If set, before launching the mini app the client should ask the user to add the mini app to the attachment/side menu, and only if the user accepts, after invoking messages.toggleBotInAttachMenu the app should be opened. |
| has_settings | flags.1?true | Deprecated flag, can be ignored. |
| request_write_access | flags.2?true | Whether the bot would like to send messages to the user. |
| show_in_attach_menu | flags.3?true | Whether, when installed, an attachment menu entry should be shown for the Mini App. |
| show_in_side_menu | flags.4?true | Whether, when installed, an entry in the main view side menu should be shown for the Mini App. |
| side_menu_disclaimer_needed | flags.5?true | If inactive if set and the user hasn't previously accepted the third-party mini apps Terms of Service for this bot, when showing the mini app installation prompt, an additional mandatory checkbox to accept the mini apps TOS and a disclaimer indicating that this Mini App is not affiliated to Telegram should be shown. |
| bot_id | long | Bot ID |
| short_name | string | Attachment menu item name |
| peer_types | flags.3?Vector<AttachMenuPeerType> | List of dialog types where this attachment menu entry should be shown |
| icons | Vector<AttachMenuBotIcon> | List of platform-specific static icons and animations to use for the attachment menu button |


## Type


## Related pages
