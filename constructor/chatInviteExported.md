# chatInviteExported
Exported chat invite

```
chatInviteExported#a22cbd96 flags:# revoked:flags.0?true permanent:flags.5?true request_needed:flags.6?true link:string admin_id:long date:int start_date:flags.4?int expire_date:flags.1?int usage_limit:flags.2?int usage:flags.3?int requested:flags.7?int subscription_expired:flags.10?int title:flags.8?string subscription_pricing:flags.9?StarsSubscriptionPricing = ExportedChatInvite;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| revoked | flags.0?true | Whether this chat invite was revoked |
| permanent | flags.5?true | Whether this chat invite has no expiration |
| request_needed | flags.6?true | Whether users importing this invite link will have to be approved to join the channel or group |
| link | string | Chat invitation link |
| admin_id | long | ID of the admin that created this chat invite |
| date | int | When was this chat invite created |
| start_date | flags.4?int | When was this chat invite last modified |
| expire_date | flags.1?int | When does this chat invite expire |
| usage_limit | flags.2?int | Maximum number of users that can join using this link |
| usage | flags.3?int | How many users joined using this link |
| requested | flags.7?int | Number of users that have already used this link to join |
| subscription_expired | flags.10?int | For Telegram Star subscriptions », contains the number of chat members which have already joined the chat using the link, but have already left due to expiration of their subscription. |
| title | flags.8?string | Custom description for the invite link, visible only to admins |
| subscription_pricing | flags.9?StarsSubscriptionPricing | For Telegram Star subscriptions », contains the pricing of the subscription the user must activate to join the private channel. |


## Type
ExportedChatInvite

## Related pages
