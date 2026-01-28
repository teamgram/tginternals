# messages.exportChatInvite
Export an invite link for a chat

```
chatInviteExported#a22cbd96 flags:# revoked:flags.0?true permanent:flags.5?true request_needed:flags.6?true link:string admin_id:long date:int start_date:flags.4?int expire_date:flags.1?int usage_limit:flags.2?int usage:flags.3?int requested:flags.7?int subscription_expired:flags.10?int title:flags.8?string subscription_pricing:flags.9?StarsSubscriptionPricing = ExportedChatInvite;
chatInvitePublicJoinRequests#ed107ab7 = ExportedChatInvite;
---functions---
messages.exportChatInvite#a455de90 flags:# legacy_revoke_permanent:flags.2?true request_needed:flags.3?true peer:InputPeer expire_date:flags.0?int usage_limit:flags.1?int title:flags.4?string subscription_pricing:flags.5?StarsSubscriptionPricing = ExportedChatInvite;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| legacy_revoke_permanent | flags.2?true | Legacy flag, reproducing legacy behavior of this method: if set, revokes all previous links before creating a new one. Kept for bot API BC, should not be used by modern clients. |
| request_needed | flags.3?true | Whether admin confirmation is required before admitting each separate user into the chat |
| peer | InputPeer | Chat |
| expire_date | flags.0?int | Expiration date |
| usage_limit | flags.1?int | Maximum number of users that can join using this link |
| title | flags.4?string | Description of the invite link, visible only to administrators |
| subscription_pricing | flags.5?StarsSubscriptionPricing | For Telegram Star subscriptions », contains the pricing of the subscription the user must activate to join the private channel. |


## Result
ExportedChatInvite

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_MONOFORUM_UNSUPPORTED | Monoforums do not support this feature. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | EXPIRE_DATE_INVALID | The specified expiration date is invalid. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | PRICING_CHAT_INVALID | The pricing for the subscription is invalid, the maximum price is specified in the stars_subscription_amount_max config key ». |
| 400 | SUBSCRIPTION_PERIOD_INVALID | The specified subscription_pricing.period is invalid. |
| 400 | USAGE_LIMIT_INVALID | The specified usage limit is invalid. |

