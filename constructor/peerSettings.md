# peerSettings
List of actions that are possible when interacting with this user, to be shown as suggested actions in the chat action bar », see here » for more info.

```
peerSettings#f47741f7 flags:# report_spam:flags.0?true add_contact:flags.1?true block_contact:flags.2?true share_contact:flags.3?true need_contacts_exception:flags.4?true report_geo:flags.5?true autoarchived:flags.7?true invite_members:flags.8?true request_chat_broadcast:flags.10?true business_bot_paused:flags.11?true business_bot_can_reply:flags.12?true geo_distance:flags.6?int request_chat_title:flags.9?string request_chat_date:flags.9?int business_bot_id:flags.13?long business_bot_manage_url:flags.13?string charge_paid_message_stars:flags.14?long registration_month:flags.15?string phone_country:flags.16?string name_change_date:flags.17?int photo_change_date:flags.18?int = PeerSettings;
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
| business_bot_paused | flags.11?true | This flag is set if both business_bot_id and business_bot_manage_url are set and all connected business bots » were paused in this chat using account.toggleConnectedBotPaused ». |
| business_bot_can_reply | flags.12?true | This flag is set if both business_bot_id and business_bot_manage_url are set and connected business bots » can reply to messages in this chat, as specified by the settings during initial configuration. |
| geo_distance | flags.6?int | Distance in meters between us and this peer |
| request_chat_title | flags.9?string | If set, this is a private chat with an administrator of a chat or channel to which the user sent a join request, and this field contains the chat/channel's title. |
| request_chat_date | flags.9?int | If set, this is a private chat with an administrator of a chat or channel to which the user sent a join request, and this field contains the timestamp when the join request » was sent. |
| business_bot_id | flags.13?long | Contains the ID of the business bot » managing this chat, used to display info about the bot in the action bar. |
| business_bot_manage_url | flags.13?string | Contains a deep link », used to open a management menu in the business bot. This flag is set if and only if business_bot_id is set. |
| charge_paid_message_stars | flags.14?long | All users that must pay us » to send us private messages will have this flag set only for us, containing the amount of required stars, see here » for more info on paid messages. |
| registration_month | flags.15?string | Used to display the user's registration year and month, the string is in MM.YYYY format, where MM is the registration month (1-12), and YYYY is the registration year. |
| phone_country | flags.16?string | The country code of the user's phone number. |
| name_change_date | flags.17?int | When was the user's name last changed. |
| photo_change_date | flags.18?int | When was the user's photo last changed. |


## Type
PeerSettings

## Related pages
