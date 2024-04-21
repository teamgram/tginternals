# updateBotInlineSend
The result of an inline query that was chosen by a user and sent to their chat partner. Please see our documentation on the feedback collecting for details on how to enable these updates for your bot.

```
updateBotInlineSend#12f12a07 flags:# user_id:long query:string geo:flags.0?GeoPoint id:string msg_id:flags.1?InputBotInlineMessageID = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| user_id | long | The user that chose the result |
| query | string | The query that was used to obtain the result |
| geo | flags.0?GeoPoint | Optional. Sender location, only for bots that require user location |
| id | string | The unique identifier for the result that was chosen |
| msg_id | flags.1?InputBotInlineMessageID | Identifier of the sent inline message. Available only if there is an inline keyboard attached to the message. Will be also received in callback queries and can be used to edit the message. |


## Type
Update

## Related pages
