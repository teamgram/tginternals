# messageActionRequestedPeerSentMe
Contains info about one or more peers that the a user shared with the me (the bot) after clicking on a keyboardButtonRequestPeer button (service message received by the bot).

```
messageActionRequestedPeerSentMe#93b31848 button_id:int peers:Vector<RequestedPeer> = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| button_id | int | button_id contained in the keyboardButtonRequestPeer |
| peers | Vector<RequestedPeer> | Info about the shared peers. |


## Type
MessageAction

## Related pages
