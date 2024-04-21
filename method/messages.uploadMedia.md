# messages.uploadMedia
Upload a file and associate it to a chat (without actually sending it to the chat)

```
messageMediaEmpty#3ded6320 = MessageMedia;
messageMediaPhoto#695150d7 flags:# spoiler:flags.3?true photo:flags.0?Photo ttl_seconds:flags.2?int = MessageMedia;
messageMediaGeo#56e0d474 geo:GeoPoint = MessageMedia;
messageMediaContact#70322949 phone_number:string first_name:string last_name:string vcard:string user_id:long = MessageMedia;
messageMediaUnsupported#9f84f49e = MessageMedia;
messageMediaDocument#4cf4d72d flags:# nopremium:flags.3?true spoiler:flags.4?true video:flags.6?true round:flags.7?true voice:flags.8?true document:flags.0?Document alt_document:flags.5?Document ttl_seconds:flags.2?int = MessageMedia;
messageMediaWebPage#ddf10c3b flags:# force_large_media:flags.0?true force_small_media:flags.1?true manual:flags.3?true safe:flags.4?true webpage:WebPage = MessageMedia;
messageMediaVenue#2ec0533f geo:GeoPoint title:string address:string provider:string venue_id:string venue_type:string = MessageMedia;
messageMediaGame#fdb19008 game:Game = MessageMedia;
messageMediaInvoice#f6a548d3 flags:# shipping_address_requested:flags.1?true test:flags.3?true title:string description:string photo:flags.0?WebDocument receipt_msg_id:flags.2?int currency:string total_amount:long start_param:string extended_media:flags.4?MessageExtendedMedia = MessageMedia;
messageMediaGeoLive#b940c666 flags:# geo:GeoPoint heading:flags.0?int period:int proximity_notification_radius:flags.1?int = MessageMedia;
messageMediaPoll#4bd6e798 poll:Poll results:PollResults = MessageMedia;
messageMediaDice#3f7ee58b value:int emoticon:string = MessageMedia;
messageMediaStory#68cb6283 flags:# via_mention:flags.1?true peer:Peer id:int story:flags.0?StoryItem = MessageMedia;
messageMediaGiveaway#daad85b0 flags:# only_new_subscribers:flags.0?true winners_are_visible:flags.2?true channels:Vector<long> countries_iso2:flags.1?Vector<string> prize_description:flags.3?string quantity:int months:int until_date:int = MessageMedia;
messageMediaGiveawayResults#c6991068 flags:# only_new_subscribers:flags.0?true refunded:flags.2?true channel_id:long additional_peers_count:flags.3?int launch_msg_id:int winners_count:int unclaimed_count:int winners:Vector<long> months:int prize_description:flags.1?string until_date:int = MessageMedia;
---functions---
messages.uploadMedia#519bc2b1 peer:InputPeer media:InputMedia = MessageMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The chat, can be inputPeerEmpty for bots and inputPeerSelf for users. |
| media | InputMedia | File uploaded in chunks as described in files » |


## Result
MessageMedia

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | CHAT_RESTRICTED | You can't send messages in this chat, you were restricted. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | FILE_PARTS_INVALID | The number of file parts is invalid. |
| 400 | FILE_PART_LENGTH_INVALID | The length of a file part is invalid. |
| 400 | IMAGE_PROCESS_FAILED | Failure while processing image. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | MEDIA_INVALID | Media invalid. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | PHOTO_EXT_INVALID | The extension of the photo is invalid. |
| 400 | PHOTO_INVALID_DIMENSIONS | The photo dimensions are invalid. |
| 400 | PHOTO_SAVE_FILE_INVALID | Internal issues, try again later. |
| 400 | USER_BANNED_IN_CHANNEL | You're banned from sending messages in supergroups/channels. |
| 400 | WEBPAGE_CURL_FAILED | Failure while fetching the webpage with cURL. |

