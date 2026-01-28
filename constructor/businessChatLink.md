# businessChatLink
Contains info about a business chat deep link » created by the current account.

```
businessChatLink#b4ae666f flags:# link:string message:string entities:flags.0?Vector<MessageEntity> title:flags.1?string views:int = BusinessChatLink;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| link | string | Business chat deep link. |
| message | string | Message to pre-fill in the message input field. |
| entities | flags.0?Vector<MessageEntity> | Message entities for styled text |
| title | flags.1?string | Human-readable name of the link, to simplify management in the UI (only visible to the creator of the link). |
| views | int | Number of times the link was resolved (clicked/scanned/etc...). |


## Type
BusinessChatLink

## Related pages
