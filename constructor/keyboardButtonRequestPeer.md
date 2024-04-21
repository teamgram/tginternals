# keyboardButtonRequestPeer
Prompts the user to select and share one or more peers with the bot using messages.sendBotRequestedPeer

```
keyboardButtonRequestPeer#53d7bfd8 text:string button_id:int peer_type:RequestPeerType max_quantity:int = KeyboardButton;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| text | string | Button text |
| button_id | int | Button ID, to be passed to messages.sendBotRequestedPeer. |
| peer_type | RequestPeerType | Filtering criteria to use for the peer selection list shown to the user. The list should display all existing peers of the specified type, and should also offer an option for the user to create and immediately use one or more (up to max_quantity) peers of the specified type, if needed. |
| max_quantity | int | Maximum number of peers that can be chosne. |


## Type
KeyboardButton

## Related pages
