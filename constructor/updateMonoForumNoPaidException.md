# updateMonoForumNoPaidException
An admin has (un)exempted this monoforum topic » from payment to send messages using account.toggleNoPaidMessagesException.

```
updateMonoForumNoPaidException#9f812b08 flags:# exception:flags.0?true channel_id:long saved_peer_id:Peer = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| exception | flags.0?true | If set, an admin has exempted this peer, otherwise the peer was unexempted. |
| channel_id | long | The monoforum ID. |
| saved_peer_id | Peer | The peer/topic ID. |


## Type
Update

## Related pages
