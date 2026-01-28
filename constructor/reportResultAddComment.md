# reportResultAddComment
The user should enter an additional comment for the moderators, and then messages.report must be re-invoked, passing the comment to messages.report.message.

```
reportResultAddComment#6f09ac31 flags:# optional:flags.0?true option:bytes = ReportResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| optional | flags.0?true | Whether this step can be skipped by the user, passing an empty message to messages.report, or if a non-empty message is mandatory. |
| option | bytes | The messages.report method must be re-invoked, passing this option to option |


## Type
ReportResult

## Related pages
