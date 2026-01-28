# inputKeyboardButtonRequestPeer
Prompts the user to select and share one or more peers with the bot using messages.sendBotRequestedPeer.

```
inputKeyboardButtonRequestPeer#c9662d05 flags:# name_requested:flags.0?true username_requested:flags.1?true photo_requested:flags.2?true text:string button_id:int peer_type:RequestPeerType max_quantity:int = KeyboardButton;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| name_requested | flags.0?true | Set this flag to request the peer's name. |
| username_requested | flags.1?true | Set this flag to request the peer's @username (if any). |
| photo_requested | flags.2?true | Set this flag to request the peer's photo (if any). |
| text | string | Button text |
| button_id | int | Button ID, to be passed to messages.sendBotRequestedPeer. |
| peer_type | RequestPeerType | Filtering criteria to use for the peer selection list shown to the user. The list should display all existing peers of the specified type, and should also offer an option for the user to create and immediately use one or more (up to max_quantity) peers of the specified type, if needed. |
| max_quantity | int | Maximum number of peers that can be chosen. |


## Type
KeyboardButton

## Related pages
