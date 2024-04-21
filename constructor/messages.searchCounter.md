# messages.searchCounter
Indicates how many results would be found by a messages.search call with the same parameters

```
messages.searchCounter#e844ebff flags:# inexact:flags.1?true filter:MessagesFilter count:int = messages.SearchCounter;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| inexact | flags.1?true | If set, the results may be inexact |
| filter | MessagesFilter | Provided message filter |
| count | int | Number of results that were found server-side |


## Type
messages.SearchCounter

## Related pages
