# contacts.getLocated
Get users and geochats near you, see here » for more info.

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
contacts.getLocated#d348bc44 flags:# background:flags.1?true geo_point:InputGeoPoint self_expires:flags.0?int = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| background | flags.1?true | While the geolocation of the current user is public, clients should update it in the background every half-an-hour or so, while setting this flag. Do this only if the new location is more than 1 KM away from the previous one, or if the previous location is unknown. |
| geo_point | InputGeoPoint | Geolocation |
| self_expires | flags.0?int | If set, the geolocation of the current user will be public for the specified number of seconds; pass 0x7fffffff to disable expiry, 0 to make the current geolocation private; if the flag isn't set, no changes will be applied. |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | GEO_POINT_INVALID | Invalid geoposition provided. |
| 406 | USERPIC_PRIVACY_REQUIRED | You need to disable privacy settings for your profile picture in order to make your geolocation public. |
| 406 | USERPIC_UPLOAD_REQUIRED | You must have a profile picture to publish your geolocation. |

