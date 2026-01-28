# messageActionConferenceCall
Represents a conference call (or an invitation to a conference call, if neither the missed nor active flags are set).

```
messageActionConferenceCall#2ffe2f7a flags:# missed:flags.0?true active:flags.1?true video:flags.4?true call_id:long duration:flags.2?int other_participants:flags.3?Vector<Peer> = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| missed | flags.0?true | Whether the conference call has ended and the user hasn't joined. |
| active | flags.1?true | Whether the user is currently in the conference call. |
| video | flags.4?true | Whether this is a video conference call. |
| call_id | long | Call ID. |
| duration | flags.2?int | Call duration, for left calls only. |
| other_participants | flags.3?Vector<Peer> | Identifiers of some other call participants. |


## Type


## Related pages
