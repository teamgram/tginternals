# messageActionSetMessagesTTL
The Time-To-Live of messages in this chat was changed.

```
messageActionSetMessagesTTL#3c134d7b flags:# period:int auto_setting_from:flags.0?long = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| period | int | New Time-To-Live of all messages sent in this chat; if 0, autodeletion was disabled. |
| auto_setting_from | flags.0?long | If set, the chat TTL setting was set not due to a manual change by one of participants, but automatically because one of the participants has the default TTL settings enabled ». For example, when a user writes to us for the first time and we have set a default messages TTL of 1 week, this service message (with auto_setting_from=our_userid) will be emitted before our first message. |


## Type
MessageAction

## Related pages
