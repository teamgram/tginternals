# help.promoData
A set of useful suggestions and a PSA/MTProxy sponsored peer, see here » for more info.

```
help.promoData#8a4d87a flags:# proxy:flags.0?true expires:int peer:flags.3?Peer psa_type:flags.1?string psa_message:flags.2?string pending_suggestions:Vector<string> dismissed_suggestions:Vector<string> custom_pending_suggestion:flags.4?PendingSuggestion chats:Vector<Chat> users:Vector<User> = help.PromoData;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| proxy | flags.0?true | Set when connecting using an MTProxy that has configured an associated peer (that will be passed in peer, i.e. the channel that sponsored the MTProxy) that should be pinned on top of the chat list. |
| expires | int | Unixtime when to re-invoke help.getPromoData. |
| peer | flags.3?Peer | MTProxy/PSA peer |
| psa_type | flags.1?string | For Public Service Announcement peers, indicates the type of the PSA. |
| psa_message | flags.2?string | For Public Service Announcement peers, contains the PSA itself. |
| pending_suggestions | Vector<string> | Contains a list of pending suggestions ». |
| dismissed_suggestions | Vector<string> | Contains a list of inverted suggestions ». |
| custom_pending_suggestion | flags.4?PendingSuggestion | Contains a list of custom pending suggestions ». |
| chats | Vector<Chat> | Chat info |
| users | Vector<User> | User info |


## Type
help.PromoData

## Related pages
