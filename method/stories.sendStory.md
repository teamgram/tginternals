# stories.sendStory
Uploads a Telegram Story.

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
---functions---
stories.sendStory#e4e6694b flags:# pinned:flags.2?true noforwards:flags.4?true fwd_modified:flags.7?true peer:InputPeer media:InputMedia media_areas:flags.5?Vector<MediaArea> caption:flags.0?string entities:flags.1?Vector<MessageEntity> privacy_rules:Vector<InputPrivacyRule> random_id:long period:flags.3?int fwd_from_id:flags.6?InputPeer fwd_from_story:flags.6?int = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| pinned | flags.2?true | Whether to add the story to the profile automatically upon expiration. If not set, the story will only be added to the archive, see here » for more info. |
| noforwards | flags.4?true | If set, disables forwards, screenshots, and downloads. |
| fwd_modified | flags.7?true | Set this flag when reposting stories with fwd_from_id+fwd_from_id, if the media was modified before reposting. |
| peer | InputPeer | The peer to send the story as. |
| media | InputMedia | The story media. |
| media_areas | flags.5?Vector<MediaArea> | Media areas associated to the story, see here » for more info. |
| caption | flags.0?string | Story caption. |
| entities | flags.1?Vector<MessageEntity> | Message entities for styled text, if allowed by the stories_entities client configuration parameter ». |
| privacy_rules | Vector<InputPrivacyRule> | Privacy rules for the story, indicating who can or can't view the story. |
| random_id | long | Unique client message ID required to prevent message resending. |
| period | flags.3?int | Period after which the story is moved to archive (and to the profile if pinned is set), in seconds; must be one of 6 * 3600, 12 * 3600, 86400, or 2 * 86400 for Telegram Premium users, and 86400 otherwise. |
| fwd_from_id | flags.6?InputPeer | If set, indicates that this story is a repost of story with ID fwd_from_story posted by the peer in fwd_from_id. |
| fwd_from_story | flags.6?int | If set, indicates that this story is a repost of story with ID fwd_from_story posted by the peer in fwd_from_id. |


## Result
Updates

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | IMAGE_PROCESS_FAILED | Failure while processing image. |
| 400 | MEDIA_EMPTY | The provided media object is invalid. |
| 400 | MEDIA_FILE_INVALID | The specified media file is invalid. |
| 400 | MEDIA_TYPE_INVALID | The specified media type cannot be used in stories. |
| 400 | MEDIA_VIDEO_STORY_MISSING | A non-story video cannot be repubblished as a story (emitted when trying to resend a non-story video as a story using inputDocument). |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | PREMIUM_ACCOUNT_REQUIRED | A premium account is required to execute this action. |
| 400 | STORIES_TOO_MUCH | You have hit the maximum active stories limit as specified by the story_expiring_limit_* client configuration parameters: you should buy a Premium subscription, delete an active story, or wait for the oldest story to expire. |
| 400 | STORY_PERIOD_INVALID | The specified story period is invalid for this account. |
| 400 | VENUE_ID_INVALID | The specified venue ID is invalid. |

