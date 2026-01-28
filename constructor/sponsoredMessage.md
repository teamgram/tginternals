# sponsoredMessage
A sponsored message.

```
sponsoredMessage#7dbf8673 flags:# recommended:flags.5?true can_report:flags.12?true random_id:bytes url:string title:string message:string entities:flags.1?Vector<MessageEntity> photo:flags.6?Photo media:flags.14?MessageMedia color:flags.13?PeerColor button_text:string sponsor_info:flags.7?string additional_info:flags.8?string min_display_duration:flags.15?int max_display_duration:flags.15?int = SponsoredMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| recommended | flags.5?true | Whether the message needs to be labeled as "recommended" instead of "sponsored" |
| can_report | flags.12?true | Whether this message can be reported as specified here ». |
| random_id | bytes | Message ID |
| url | string | Contains the URL to open when the user clicks on the sponsored message. |
| title | string | Contains the title of the sponsored message. |
| message | string | Sponsored message |
| entities | flags.1?Vector<MessageEntity> | Message entities for styled text in message. |
| photo | flags.6?Photo | If set, contains a custom profile photo bubble that should be displayed for the sponsored message, like for messages sent in groups. |
| media | flags.14?MessageMedia | If set, contains some media. |
| color | flags.13?PeerColor | If set, the sponsored message should use the message accent color » specified in color. |
| button_text | string | Label of the sponsored message button. |
| sponsor_info | flags.7?string | If set, contains additional information about the sponsor to be shown along with the message. |
| additional_info | flags.8?string | If set, contains additional information about the sponsored message to be shown along with the message. |
| min_display_duration | flags.15?int | For sponsored messages to show on channel videos », allow the user to hide the ad only after the specified amount of seconds. |
| max_display_duration | flags.15?int | For sponsored messages to show on channel videos », autohide the ad after after the specified amount of seconds. |


## Type
SponsoredMessage

## Related pages
