# config
Current configuration

```
config#cc1a241e flags:# default_p2p_contacts:flags.3?true preload_featured_stickers:flags.4?true revoke_pm_inbox:flags.6?true blocked_mode:flags.8?true force_try_ipv6:flags.14?true date:int expires:int test_mode:Bool this_dc:int dc_options:Vector<DcOption> dc_txt_domain_name:string chat_size_max:int megagroup_size_max:int forwarded_count_max:int online_update_period_ms:int offline_blur_timeout_ms:int offline_idle_timeout_ms:int online_cloud_timeout_ms:int notify_cloud_delay_ms:int notify_default_delay_ms:int push_chat_period_ms:int push_chat_limit:int edit_time_limit:int revoke_time_limit:int revoke_pm_time_limit:int rating_e_decay:int stickers_recent_limit:int channels_read_media_period:int tmp_sessions:flags.0?int call_receive_timeout_ms:int call_ring_timeout_ms:int call_connect_timeout_ms:int call_packet_timeout_ms:int me_url_prefix:string autoupdate_url_prefix:flags.7?string gif_search_username:flags.9?string venue_search_username:flags.10?string img_search_username:flags.11?string static_maps_provider:flags.12?string caption_length_max:int message_length_max:int webfile_dc_id:int suggested_lang_code:flags.2?string lang_pack_version:flags.2?int base_lang_pack_version:flags.2?int reactions_default:flags.15?Reaction autologin_token:flags.16?string = Config;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| default_p2p_contacts | flags.3?true | Whether the client should use P2P by default for phone calls with contacts |
| preload_featured_stickers | flags.4?true | Whether the client should preload featured stickers |
| revoke_pm_inbox | flags.6?true | Whether incoming private messages can be deleted for both participants |
| blocked_mode | flags.8?true | Indicates that telegram is probably censored by governments/ISPs in the current region |
| force_try_ipv6 | flags.14?true | Whether to forcefully connect using IPv6 dcOptions, even if the client knows that IPv4 is available. |
| date | int | Current date at the server |
| expires | int | Expiration date of this config: when it expires it'll have to be refetched using help.getConfig |
| test_mode | Bool | Whether we're connected to the test DCs |
| this_dc | int | ID of the DC that returned the reply |
| dc_options | Vector<DcOption> | DC IP list |
| dc_txt_domain_name | string | Domain name for fetching encrypted DC list from DNS TXT record |
| chat_size_max | int | Maximum member count for normal groups |
| megagroup_size_max | int | Maximum member count for supergroups |
| forwarded_count_max | int | Maximum number of messages that can be forwarded at once using messages.forwardMessages. |
| online_update_period_ms | int | The client should update its online status every N milliseconds |
| offline_blur_timeout_ms | int | Delay before offline status needs to be sent to the server |
| offline_idle_timeout_ms | int | Time without any user activity after which it should be treated offline |
| online_cloud_timeout_ms | int | If we are offline, but were online from some other client in last online_cloud_timeout_ms milliseconds after we had gone offline, then delay offline notification for notify_cloud_delay_ms milliseconds. |
| notify_cloud_delay_ms | int | If we are offline, but online from some other client then delay sending the offline notification for notify_cloud_delay_ms milliseconds. |
| notify_default_delay_ms | int | If some other client is online, then delay notification for notification_default_delay_ms milliseconds |
| push_chat_period_ms | int | Not for client use |
| push_chat_limit | int | Not for client use |
| edit_time_limit | int | Only messages with age smaller than the one specified can be edited |
| revoke_time_limit | int | Only channel/supergroup messages with age smaller than the specified can be deleted |
| revoke_pm_time_limit | int | Only private messages with age smaller than the specified can be deleted |
| rating_e_decay | int | Exponential decay rate for computing top peer rating |
| stickers_recent_limit | int | Maximum number of recent stickers |
| channels_read_media_period | int | Indicates that round videos (video notes) and voice messages sent in channels and older than the specified period must be marked as read |
| tmp_sessions | flags.0?int | Temporary passport sessions |
| call_receive_timeout_ms | int | Maximum allowed outgoing ring time in VoIP calls: if the user we're calling doesn't reply within the specified time (in milliseconds), we should hang up the call |
| call_ring_timeout_ms | int | Maximum allowed incoming ring time in VoIP calls: if the current user doesn't reply within the specified time (in milliseconds), the call will be automatically refused |
| call_connect_timeout_ms | int | VoIP connection timeout: if the instance of libtgvoip on the other side of the call doesn't connect to our instance of libtgvoip within the specified time (in milliseconds), the call must be aborted |
| call_packet_timeout_ms | int | If during a VoIP call a packet isn't received for the specified period of time, the call must be aborted |
| me_url_prefix | string | The domain to use to parse deep links ». |
| autoupdate_url_prefix | flags.7?string | URL to use to auto-update the current app |
| gif_search_username | flags.9?string | Username of the bot to use to search for GIFs |
| venue_search_username | flags.10?string | Username of the bot to use to search for venues |
| img_search_username | flags.11?string | Username of the bot to use for image search |
| static_maps_provider | flags.12?string | ID of the map provider to use for venues |
| caption_length_max | int | Maximum length of caption (length in utf8 codepoints) |
| message_length_max | int | Maximum length of messages (length in utf8 codepoints) |
| webfile_dc_id | int | DC ID to use to download webfiles |
| suggested_lang_code | flags.2?string | Suggested language code |
| lang_pack_version | flags.2?int | Language pack version |
| base_lang_pack_version | flags.2?int | Basic language pack version |
| reactions_default | flags.15?Reaction | Default message reaction |
| autologin_token | flags.16?string | Autologin token, click here for more info on URL authorization ». |


## Type
Config

## Related pages
