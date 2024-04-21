# peerSettings
List of actions that are possible when interacting with this user, to be shown as suggested actions in the chat action bar », see here » for more info.

```
peerSettings#a518110d flags:# report_spam:flags.0?true add_contact:flags.1?true block_contact:flags.2?true share_contact:flags.3?true need_contacts_exception:flags.4?true report_geo:flags.5?true autoarchived:flags.7?true invite_members:flags.8?true request_chat_broadcast:flags.10?true geo_distance:flags.6?int request_chat_title:flags.9?string request_chat_date:flags.9?int = PeerSettings;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| report_spam | flags.0?true | Whether we can still report the user for spam |
| add_contact | flags.1?true | Whether we can add the user as contact |
| block_contact | flags.2?true | Whether we can block the user |
| share_contact | flags.3?true | Whether we can share the user's contact |
| need_contacts_exception | flags.4?true | Whether a special exception for contacts is needed |
| report_geo | flags.5?true | Whether we can report a geogroup as irrelevant for this location |
| autoarchived | flags.7?true | Whether this peer was automatically archived according to privacy settings and can be unarchived |
| invite_members | flags.8?true | If set, this is a recently created group chat to which new members can be invited |
| request_chat_broadcast | flags.10?true | This flag is set if request_chat_title and request_chat_date fields are set and the join request » is related to a channel (otherwise if only the request fields are set, the join request » is related to a chat). |
| geo_distance | flags.6?int | Distance in meters between us and this peer |
| request_chat_title | flags.9?string | If set, this is a private chat with an administrator of a chat or channel to which the user sent a join request, and this field contains the chat/channel's title. |
| request_chat_date | flags.9?int | If set, this is a private chat with an administrator of a chat or channel to which the user sent a join request, and this field contains the timestamp when the join request » was sent. |


## Type
PeerSettings

## Related pages
