# messageViews
View, forward counter + info about replies of a specific message

```
messageViews#455b853d flags:# views:flags.0?int forwards:flags.1?int replies:flags.2?MessageReplies = MessageViews;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| views | flags.0?int | View count of message |
| forwards | flags.1?int | Forward count of message |
| replies | flags.2?MessageReplies | Reply and thread information of message |


## Type
MessageViews

## Related pages
