# updateShortSentMessage
Shortened constructor containing info on one outgoing message to a contact (the destination chat has to be extracted from the method call that returned this object).

```
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| out | flags.1?true | Whether the message is outgoing |
| id | int | ID of the sent message |
| pts | int | PTS |
| pts_count | int | PTS count |
| date | int | date |
| media | flags.9?MessageMedia | Attached media |
| entities | flags.7?Vector<MessageEntity> | Entities for styled text |
| ttl_period | flags.25?int | Time To Live of the message, once message.date+message.ttl_period === time(), the message will be deleted on the server, and must be deleted locally as well. |


## Type
Updates

## Related pages
