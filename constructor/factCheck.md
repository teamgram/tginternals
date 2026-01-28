# factCheck
Represents a fact-check » created by an independent fact-checker.

```
factCheck#b89bfccf flags:# need_check:flags.0?true country:flags.1?string text:flags.1?TextWithEntities hash:long = FactCheck;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| need_check | flags.0?true | If set, the country/text fields will not be set, and the fact check must be fetched manually by the client (if it isn't already cached with the key specified in hash) using bundled messages.getFactCheck requests, when the message with the factcheck scrolls into view. |
| country | flags.1?string | A two-letter ISO 3166-1 alpha-2 country code of the country for which the fact-check should be shown. |
| text | flags.1?TextWithEntities | The fact-check. |
| hash | long | Hash used for caching, for more info click here |


## Type
FactCheck

## Related pages
