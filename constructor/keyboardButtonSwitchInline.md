# keyboardButtonSwitchInline
Button to force a user to switch to inline mode: pressing the button will prompt the user to select one of their chats, open that chat and insert the bot's username and the specified inline query in the input field.

```
keyboardButtonSwitchInline#93b9fbb5 flags:# same_peer:flags.0?true text:string query:string peer_types:flags.1?Vector<InlineQueryPeerType> = KeyboardButton;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| same_peer | flags.0?true | If set, pressing the button will insert the bot's username and the specified inline query in the current chat's input field. |
| text | string | Button label |
| query | string | The inline query to use |
| peer_types | flags.1?Vector<InlineQueryPeerType> | Filter to use when selecting chats. |


## Type
KeyboardButton

## Related pages
