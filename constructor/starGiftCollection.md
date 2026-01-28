# starGiftCollection
Represents a star gift collection ».

```
starGiftCollection#9d6b13b0 flags:# collection_id:int title:string icon:flags.0?Document gifts_count:int hash:long = StarGiftCollection;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| collection_id | int | The ID of the collection. |
| title | string | Title of the collection. |
| icon | flags.0?Document | Optional icon for the collection, taken from the first gift in the collection. |
| gifts_count | int | Number of gifts in the collection. |
| hash | long | Field to use instead of collection_id when generating the hash to pass to payments.getStarGiftCollections. |


## Type
StarGiftCollection

## Related pages
