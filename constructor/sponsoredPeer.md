# sponsoredPeer
A sponsored peer.

```
sponsoredPeer#c69708d3 flags:# random_id:bytes peer:Peer sponsor_info:flags.0?string additional_info:flags.1?string = SponsoredPeer;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| random_id | bytes | ID of the sponsored peer, to be passed to messages.viewSponsoredMessage, messages.clickSponsoredMessage or messages.reportSponsoredMessage (the same methods used for sponsored messages &raquo). |
| peer | Peer | The sponsored peer. |
| sponsor_info | flags.0?string | If set, contains additional information about the sponsor to be shown along with the peer. |
| additional_info | flags.1?string | If set, contains additional information about the sponsored message to be shown along with the peer. |


## Type
SponsoredPeer

## Related pages
