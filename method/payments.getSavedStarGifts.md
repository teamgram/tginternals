# payments.getSavedStarGifts
Fetch the full list of gifts owned by a peer.

```
payments.savedStarGifts#95f389b1 flags:# count:int chat_notifications_enabled:flags.1?Bool gifts:Vector<SavedStarGift> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = payments.SavedStarGifts;
---functions---
payments.getSavedStarGifts#a319e569 flags:# exclude_unsaved:flags.0?true exclude_saved:flags.1?true exclude_unlimited:flags.2?true exclude_unique:flags.4?true sort_by_value:flags.5?true exclude_upgradable:flags.7?true exclude_unupgradable:flags.8?true peer:InputPeer collection_id:flags.6?int offset:string limit:int = payments.SavedStarGifts;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| exclude_unsaved | flags.0?true | Exclude gifts not pinned on the profile. |
| exclude_saved | flags.1?true | Exclude gifts pinned on the profile. |
| exclude_unlimited | flags.2?true | Exclude gifts that do not have the starGift.limited flag set. |
| exclude_unique | flags.4?true | Exclude collectible gifts ». |
| sort_by_value | flags.5?true | If set, sorts the gifts by price instead of reception date. |
| exclude_upgradable | flags.7?true | Exclude gifts that can be upgraded to collectible gifts ». |
| exclude_unupgradable | flags.8?true | Exclude gifts that cannot be upgraded to collectible gifts ». |
| peer | InputPeer | Fetch only gifts owned by the specified peer, such as: a user, with peer=inputPeerUser; a channel, with peer=inputPeerChannel; a connected business user (when executing the method as a bot, over the business connection), with peer=inputPeerUser. |
| collection_id | flags.6?int | Only returns gifts within the specified collection ». |
| offset | string | Offset for pagination. |
| limit | int | Maximum number of results to return, see pagination |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BUSINESS_CONNECTION_INVALID | The connection_id passed to the wrapping invokeWithBusinessConnection call is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

