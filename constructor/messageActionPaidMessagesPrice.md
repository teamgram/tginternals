# messageActionPaidMessagesPrice
The price of paid messages » in this chat was changed.

```
messageActionPaidMessagesPrice#84b88578 flags:# broadcast_messages_allowed:flags.0?true stars:long = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| broadcast_messages_allowed | flags.0?true | Can only be set for channels, if set indicates that direct messages were enabled », otherwise indicates that direct messages were disabled; the price of paid messages is related to the price of direct messages (aka those sent to the associated monoforum). |
| stars | long | The new price in Telegram Stars, can be 0 if messages are now free. |


## Type
MessageAction

## Related pages
