# groupCallParticipant
Info about a group call participant

```
groupCallParticipant#eba636fe flags:# muted:flags.0?true left:flags.1?true can_self_unmute:flags.2?true just_joined:flags.4?true versioned:flags.5?true min:flags.8?true muted_by_you:flags.9?true volume_by_admin:flags.10?true self:flags.12?true video_joined:flags.15?true peer:Peer date:int active_date:flags.3?int source:int volume:flags.7?int about:flags.11?string raise_hand_rating:flags.13?long video:flags.6?GroupCallParticipantVideo presentation:flags.14?GroupCallParticipantVideo = GroupCallParticipant;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| muted | flags.0?true | Whether the participant is muted |
| left | flags.1?true | Whether the participant has left |
| can_self_unmute | flags.2?true | Whether the participant can unmute themselves |
| just_joined | flags.4?true | Whether the participant has just joined |
| versioned | flags.5?true | If set, and updateGroupCallParticipants.version < locally stored call.version, info about this participant should be ignored. If (...), and updateGroupCallParticipants.version > call.version+1, the participant list should be refetched using phone.getGroupParticipants. |
| min | flags.8?true | If not set, the volume and muted_by_you fields can be safely used to overwrite locally cached information; otherwise, volume will contain valid information only if volume_by_admin is set both in the cache and in the received constructor. |
| muted_by_you | flags.9?true | Whether this participant was muted by the current user |
| volume_by_admin | flags.10?true | Whether our volume can only changed by an admin |
| self | flags.12?true | Whether this participant is the current user |
| video_joined | flags.15?true | Whether this participant is currently broadcasting video |
| peer | Peer | Peer information |
| date | int | When did this participant join the group call |
| active_date | flags.3?int | When was this participant last active in the group call |
| source | int | Source ID |
| volume | flags.7?int | Volume, if not set the volume is set to 100%. |
| about | flags.11?string | Info about this participant |
| raise_hand_rating | flags.13?long | Specifies the UI visualization order of peers with raised hands: peers with a higher rating should be showed first in the list. |
| video | flags.6?GroupCallParticipantVideo | Info about the video stream the participant is currently broadcasting |
| presentation | flags.14?GroupCallParticipantVideo | Info about the screen sharing stream the participant is currently broadcasting |


## Type
GroupCallParticipant

## Related pages
