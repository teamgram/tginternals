# botBusinessConnection
Contains info about a bot business connection.

```
botBusinessConnection#8f34b2f5 flags:# disabled:flags.1?true connection_id:string user_id:long dc_id:int date:int rights:flags.2?BusinessBotRights = BotBusinessConnection;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| disabled | flags.1?true | Whether this business connection is currently disabled |
| connection_id | string | Business connection ID, used to identify messages coming from the connection and to reply to them as specified here ». |
| user_id | long | ID of the user that the bot is connected to via this connection. |
| dc_id | int | ID of the datacenter where to send queries wrapped in a invokeWithBusinessConnection as specified here ». |
| date | int | When was the connection created. |
| rights | flags.2?BusinessBotRights | Business bot rights. |


## Type
BotBusinessConnection

## Related pages
