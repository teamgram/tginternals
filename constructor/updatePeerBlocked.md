# updatePeerBlocked
We blocked a peer, see here » for more info on blocklists.

```
updatePeerBlocked#ebe07752 flags:# blocked:flags.0?true blocked_my_stories_from:flags.1?true peer_id:Peer = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| blocked | flags.0?true | Whether the peer was blocked or unblocked |
| blocked_my_stories_from | flags.1?true | Whether the peer was added/removed to/from the story blocklist; if not set, this update affects the main blocklist, see here » for more info. |
| peer_id | Peer | The (un)blocked peer |


## Type
Update

## Related pages
