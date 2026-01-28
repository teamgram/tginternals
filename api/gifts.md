# Telegram Gifts

Users can send Gifts to their friends. The recipients of gifts can display them on their profile pages or turn them into Telegram Stars ». Telegram Stars can be used for many things, including supporting creators and buying services in mini apps.

### Sending gifts

```
payments.starGiftsNotModified#a388a368 = payments.StarGifts;
payments.starGifts#2ed82995 hash:int gifts:Vector<StarGift> chats:Vector<Chat> users:Vector<User> = payments.StarGifts;

starGift#80ac53c3 flags:# limited:flags.0?true sold_out:flags.1?true birthday:flags.2?true require_premium:flags.7?true limited_per_user:flags.8?true id:long sticker:Document stars:long availability_remains:flags.0?int availability_total:flags.0?int availability_resale:flags.4?long convert_stars:long first_sale_date:flags.1?int last_sale_date:flags.1?int upgrade_stars:flags.3?long resell_min_stars:flags.4?long title:flags.5?string released_by:flags.6?Peer per_user_total:flags.8?int per_user_remains:flags.8?int locked_until_date:flags.9?int = StarGift;

payments.checkCanSendGiftResultOk#374fa7ad = payments.CheckCanSendGiftResult;
payments.checkCanSendGiftResultFail#d5e58274 reason:TextWithEntities = payments.CheckCanSendGiftResult;

inputInvoiceStarGift#e8625e92 flags:# hide_name:flags.0?true include_upgrade:flags.2?true peer:InputPeer gift_id:long message:flags.1?TextWithEntities = InputInvoice;
inputInvoiceStarGiftResale#c39f5324 flags:# ton:flags.0?true slug:string to_id:InputPeer = InputInvoice;

messageActionStarGift#f24de7fa flags:# name_hidden:flags.0?true saved:flags.2?true converted:flags.3?true upgraded:flags.5?true refunded:flags.9?true can_upgrade:flags.10?true prepaid_upgrade:flags.13?true upgrade_separate:flags.16?true gift:StarGift message:flags.1?TextWithEntities convert_stars:flags.4?long upgrade_msg_id:flags.5?int upgrade_stars:flags.8?long from_id:flags.11?Peer peer:flags.12?Peer saved_id:flags.12?long prepaid_upgrade_hash:flags.14?string gift_msg_id:flags.15?int = MessageAction;

inputPrivacyKeyStarGiftsAutoSave#e1732341 = InputPrivacyKey;
privacyKeyStarGiftsAutoSave#2ca4fdf8 = PrivacyKey;

---functions---

payments.getStarGifts#c4563590 hash:int = payments.StarGifts;
payments.getResaleStarGifts#7a5fa236 flags:# sort_by_price:flags.1?true sort_by_num:flags.2?true attributes_hash:flags.0?long gift_id:long attributes:flags.3?Vector<StarGiftAttributeId> offset:string limit:int = payments.ResaleStarGifts;
payments.checkCanSendGift#c0c4edc9 gift_id:long = payments.CheckCanSendGiftResult;
payments.saveStarGift#2a2a697c flags:# unsave:flags.0?true stargift:InputSavedStarGift = Bool;
payments.convertStarGift#74bf076b stargift:InputSavedStarGift = Bool;
```

If the userFull.display_gifts_button flag of both us and another user is set (changed through globalPrivacySettings), a gift button should always be displayed in the text field in private chats with the other user: once clicked, the gift UI should be displayed, offering the user options to gift Telegram Premium » subscriptions or Telegram Gifts ».

The same gifting UI should always be (unconditionally) available through a chat picker, activated by a "Send a Gift" entry in the app's settings.

Users may disallow the reception of specific gift types by populating the globalPrivacySettings.disallowed_gifts flag, visible to other users in userFull.disallowed_gifts.

- Use payments.getStarGifts to obtain the full list of available starGifts; this method may return some sold-out gifts that have the availability_resale flag set, which indicates that some gifts of this type are on resale »

- Use payments.getResaleStarGifts to fetch gifts currently on resale.

- Pass the returned payments.resaleStarGifts.next_offset to the offset of the next method call to fetch the next result page.

- The sort_by_price and sort_by_num parameters are mutually exclusive, if neither are set results are sorted by the unixtime (descending) when their resell price was last changed.

- The same method can also be used to fetch the full list of available attributes (payments.resaleStarGifts.attributes) for the specified gift type: to fetch it, the attributes_hash field must be populated and equal to 0.

- The attributes_hash parameter can also be set to a previously returned payments.resaleStarGifts.attributes_hash, to avoid refetching the attributes if they haven't changed.

- If at least one of the following is true:

- The attributes_hash parameter of the method is not set

- The offset parameter is non-empty

- The passed attributes_hash is equal to the server-side value

- ...the payments.resaleStarGifts.attributes field will not be returned, because the payments.resaleStarGifts.attributes field is related to all gifts of a specific type, not just to the ones on the current page.

- Setting the attributes filter parameter of the method will also not affect the returned payments.resaleStarGifts.attributes in any way.

- The returned payments.resaleStarGifts.counters field is related to the payments.resaleStarGifts.attributes field, it indicates the total number of gifts that have a specific attribute: the counters field will be returned even if the attributes_hash parameter is not set, but it won't be returned if the offset field is non-empty.

- Finally, the attributes parameter of payments.getResaleStarGifts may also be set to only fetch gifts that have the specified attributes.

- If the flag is populated but no attributes of a specific type are specified, all attributes of that type are allowed.

- Note that this will not affect the returned attributes and counters.

starGifts with the limited_per_user flag set and per_user_remains <= 0 cannot be bought by the current user, since they already bought per_user_total gifts of the same type (either for themselves or for someone else).

starGifts with the locked_until_date flag set possibly cannot be bought until the specified unixtime: to verify if that is the case, invoke payments.checkCanSendGift.
This method will return a payments.checkCanSendGiftResultFail if the gift cannot be sent, along with a localized description specifying why it cannot be sent yet.
Otherwise, it will return payments.checkCanSendGiftResultOk, in which case the client should still check if the starGift.require_premium flag is set, and if yes, require the user to purchase a Telegram Premium subscription (if they aren't subscribed already).

Once the user chooses a sendable, (non-sold_out) gift, they may buy it spending starGift.stars Telegram Stars from their balance by invoking payments.getPaymentForm, passing an inputInvoiceStarGift, passing the following parameters:

- peer: Identifier of the user or channel (only if channelFull.stargifts_available is set) that will receive the gift

- gift_id: Identifier of the gift, from starGift.id

- message: Optional message, attached with the gift: the maximum length for this field is specified in the stargifts_message_length_max client configuration value ».

- hide_name: If set, your name will be hidden if the destination peer decides to display the gift on their profile (they will still see that you sent the gift)

- include_upgrade: Set this flag to additionally prepay starGift.upgrade_stars Telegram Stars, allowing the receiver to convert the gift to a collectible gift » without paying anything.

- Note that this flag can only be set if starGift.upgrade_stars is set.

When buying a gift from the list of gifts currently on resale », pass an inputInvoiceStarGiftResale instead:

- slug: Taken from the returned starGiftUnique.slug, or from the link

- to_id: Identifier of the user or channel that will receive the gift

Then, follow the usual payment flow ».

Once the payment is completed, the destination peer will receive a messageService with a messageActionStarGift from us, containing info about the received gift.

The peer may then choose to display the received gift on their profile using payments.saveStarGift.
Received gifts may also be automatically displayed on the profile, depending on the destination peer's privacy settings (inputPrivacyKeyStarGiftsAutoSave key).

Alternatively, the gift may be converted into Telegram Stars using payments.convertStarGift; the latter operation will permanently destroy the gift, converting it into starGift.convert_stars Telegram Stars, added to the user's balance (note that starGift.convert_stars will be less than the buying price (starGift.stars) of the gift).
A gift can be converted back into Telegram Stars only if it was received less than stargifts_convert_period_max seconds ago, as specified by the client configuration ».

If the user decides to display the received gift on their profile, it will be fetchable by all users as specified here ».
The same method may also be used to fetch all gifts received by owned peers from any user.

Note that gift support must be disabled if the stargifts_blocked client configuration flag » is set to true.

### List all received gifts

```
payments.savedStarGifts#95f389b1 flags:# count:int chat_notifications_enabled:flags.1?Bool gifts:Vector<SavedStarGift> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = payments.SavedStarGifts;

---functions---

payments.getSavedStarGifts#a319e569 flags:# exclude_unsaved:flags.0?true exclude_saved:flags.1?true exclude_unlimited:flags.2?true exclude_unique:flags.4?true sort_by_value:flags.5?true exclude_upgradable:flags.7?true exclude_unupgradable:flags.8?true peer:InputPeer collection_id:flags.6?int offset:string limit:int = payments.SavedStarGifts;
```

payments.getSavedStarGifts may be used to fetch the full list of gifts received by a peer, such as:

- A user, with peer=inputPeerUser (including users different from us)

- A channel, with peer=inputPeerChannel (including channels not owned by the currently logged in user)

- A connected business user (when executing the method as a bot, over the business connection), with peer=inputPeerUser of the controlled user

The method's parameters may be used to filter out gifts based on various criteria, see the method page for more info.

Note that unlike what the name suggests, the method can be used to fetch both "saved" and "unsaved" gifts (aka gifts both pinned and not pinned to the profile) for users and channels owned/controlled by the currently logged in user, depending on the passed flags.

### List specific owned gifts

```
inputSavedStarGiftUser#69279795 msg_id:int = InputSavedStarGift;
inputSavedStarGiftChat#f101aa7f peer:InputPeer saved_id:long = InputSavedStarGift;
inputSavedStarGiftSlug#2085c238 slug:string = InputSavedStarGift;

payments.savedStarGifts#95f389b1 flags:# count:int chat_notifications_enabled:flags.1?Bool gifts:Vector<SavedStarGift> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = payments.SavedStarGifts;

---functions---

payments.getSavedStarGift#b455a106 stargift:Vector<InputSavedStarGift> = payments.SavedStarGifts;
```

payments.getSavedStarGift may be used to fetch info about specific gifts owned by a peer controlled by the currently logged in user.

Note that unlike what the name suggests, the method can be used to fetch both "saved" and "unsaved" gifts (aka gifts both pinned and not pinned to the profile).

### Notifications for received channel gifts

```
---functions---

payments.toggleChatStarGiftNotifications#60eaefa1 flags:# enabled:flags.0?true peer:InputPeer = Bool;
```

payments.toggleChatStarGiftNotifications can be used to enable or disable the reception of notifications every time a gift » is received by the specified channel: it can only be invoked by admins with post_messages admin rights.

The notifications will be received in the form of messageActionStarGiftUnique and messageActionStarGift service messages from the channel.

### Pinning a received gift

```
---functions---

payments.toggleStarGiftsPinnedToTop#1513e7b0 peer:InputPeer stargift:Vector<InputSavedStarGift> = Bool;
```

A received gift can be pinned on top of the profile of the user or owned channels by using payments.toggleStarGiftsPinnedToTop.

The maximum number of gifts that can be pinned to a profile is specified in the stargifts_pinned_to_top_limit client configuration key ».

### Gift collections

```
inputSavedStarGiftUser#69279795 msg_id:int = InputSavedStarGift;
inputSavedStarGiftChat#f101aa7f peer:InputPeer saved_id:long = InputSavedStarGift;
inputSavedStarGiftSlug#2085c238 slug:string = InputSavedStarGift;

starGiftCollection#9d6b13b0 flags:# collection_id:int title:string icon:flags.0?Document gifts_count:int hash:long = StarGiftCollection;

payments.starGiftCollectionsNotModified#a0ba4f17 = payments.StarGiftCollections;
payments.starGiftCollections#8a2932f3 collections:Vector<StarGiftCollection> = payments.StarGiftCollections;

---functions---

payments.createStarGiftCollection#1f4a0e87 peer:InputPeer title:string stargift:Vector<InputSavedStarGift> = StarGiftCollection;
payments.getStarGiftCollections#981b91dd peer:InputPeer hash:long = payments.StarGiftCollections;
payments.updateStarGiftCollection#4fddbee7 flags:# peer:InputPeer collection_id:int title:flags.0?string delete_stargift:flags.1?Vector<InputSavedStarGift> add_stargift:flags.2?Vector<InputSavedStarGift> order:flags.3?Vector<InputSavedStarGift> = StarGiftCollection;
payments.reorderStarGiftCollections#c32af4cc peer:InputPeer order:Vector<int> = Bool;
payments.deleteStarGiftCollection#ad5648e8 peer:InputPeer collection_id:int = Bool;

payments.getSavedStarGifts#a319e569 flags:# exclude_unsaved:flags.0?true exclude_saved:flags.1?true exclude_unlimited:flags.2?true exclude_unique:flags.4?true sort_by_value:flags.5?true exclude_upgradable:flags.7?true exclude_unupgradable:flags.8?true peer:InputPeer collection_id:flags.6?int offset:string limit:int = payments.SavedStarGifts;
```

Gift collections group together multiple owned gifts; each gift may be part of one or more collections.

Use payments.createStarGiftCollection to create a collection.

Use payments.getSavedStarGifts with the collection_id flag set to fetch gifts within a collection.

Use payments.getStarGiftCollections to list all star gift collections of a given peer.

Note: the hash parameter of payments.getStarGiftCollections is generated by passing the starGiftCollection.hash field (not the collection_id field) of all previously returned collections, to avoid returning any results if the available collections and their content hasn't changed.

Use payments.updateStarGiftCollection to add, remove or reorder gifts in the collection or rename the collection.

Use payments.reorderStarGiftCollections to reorder the collections on an owned peer's profile.

Use payments.deleteStarGiftCollection to delete a gift collection.

A profile can contain a maximum of stargifts_collections_limit » gift collections, each containing a maximum of stargifts_collection_gifts_limit gifts.

Gift collection deep links » can be used to share a gift collection.

### Collectible gifts

A received gift may be upgraded to a collectible gift.

Collectible gifts have special attributes and can be transferred to other users or auctioned on NFT marketplaces.

When you upgrade a gift it unlocks a new appearance from dozens of custom variations made by Telegram artists. Collectibles also receive a random set of secondary attributes, including a background color, icon and number. This means every collectible gift is a unique work of art — and that some will be more rare than others.

#### Upgrade a gift to a collectible gift

```
messageActionStarGift#f24de7fa flags:# name_hidden:flags.0?true saved:flags.2?true converted:flags.3?true upgraded:flags.5?true refunded:flags.9?true can_upgrade:flags.10?true prepaid_upgrade:flags.13?true upgrade_separate:flags.16?true gift:StarGift message:flags.1?TextWithEntities convert_stars:flags.4?long upgrade_msg_id:flags.5?int upgrade_stars:flags.8?long from_id:flags.11?Peer peer:flags.12?Peer saved_id:flags.12?long prepaid_upgrade_hash:flags.14?string gift_msg_id:flags.15?int = MessageAction;
savedStarGift#19a9b572 flags:# name_hidden:flags.0?true unsaved:flags.5?true refunded:flags.9?true can_upgrade:flags.10?true pinned_to_top:flags.12?true upgrade_separate:flags.17?true from_id:flags.1?Peer date:int gift:StarGift message:flags.2?TextWithEntities msg_id:flags.3?int saved_id:flags.11?long convert_stars:flags.4?long upgrade_stars:flags.6?long can_export_at:flags.7?int transfer_stars:flags.8?long can_transfer_at:flags.13?int can_resell_at:flags.14?int collection_id:flags.15?Vector<int> prepaid_upgrade_hash:flags.16?string = SavedStarGift;

starGift#80ac53c3 flags:# limited:flags.0?true sold_out:flags.1?true birthday:flags.2?true require_premium:flags.7?true limited_per_user:flags.8?true id:long sticker:Document stars:long availability_remains:flags.0?int availability_total:flags.0?int availability_resale:flags.4?long convert_stars:long first_sale_date:flags.1?int last_sale_date:flags.1?int upgrade_stars:flags.3?long resell_min_stars:flags.4?long title:flags.5?string released_by:flags.6?Peer per_user_total:flags.8?int per_user_remains:flags.8?int locked_until_date:flags.9?int = StarGift;

starGiftAttributeModel#39d99013 name:string document:Document rarity_permille:int = StarGiftAttribute;
starGiftAttributePattern#13acff19 name:string document:Document rarity_permille:int = StarGiftAttribute;
starGiftAttributeBackdrop#d93d859c name:string backdrop_id:int center_color:int edge_color:int pattern_color:int text_color:int rarity_permille:int = StarGiftAttribute;
starGiftAttributeOriginalDetails#e0bff26c flags:# sender_id:flags.0?Peer recipient_id:Peer date:int message:flags.1?TextWithEntities = StarGiftAttribute;

payments.starGiftUpgradePreview#167bd90b sample_attributes:Vector<StarGiftAttribute> = payments.StarGiftUpgradePreview;

inputSavedStarGiftUser#69279795 msg_id:int = InputSavedStarGift;
inputSavedStarGiftChat#f101aa7f peer:InputPeer saved_id:long = InputSavedStarGift;
inputSavedStarGiftSlug#2085c238 slug:string = InputSavedStarGift;

---functions---

payments.getStarGiftUpgradePreview#9c9abcb1 gift_id:long = payments.StarGiftUpgradePreview;
payments.upgradeStarGift#aed6e4f5 flags:# keep_original_details:flags.0?true stargift:InputSavedStarGift = Updates;
```

A received gift can be upgraded to a collectible gift if the messageActionStarGift/savedStarGift.can_upgrade flag is set.

To obtain a preview of the possible attributes (chosen randomly) the gift can receive after the upgrade, invoke payments.getStarGiftUpgradePreview.

To upgrade a received gift, pay starGift.upgrade_stars Telegram Stars by invoking payments.getPaymentForm, passing an inputInvoiceStarGiftUpgrade with the following parameters:

- stargift: The identifier of the received gift

- keep_original_details: Set this flag to keep the original gift text, sender and receiver in the upgraded gift as a starGiftAttributeOriginalDetails attribute.

Then, follow the usual payment flow ».

If the original sender of the gift has already paid for the upgrade as specified here » (signaled by specific flags listed here »), simply invoke payments.upgradeStarGift with the same flags instead of using the payments.getPaymentForm payment flow.

Upgrading a gift will emit a messageActionStarGiftUnique, containing info about the newly upgraded gift and some extra information.

##### Prepaying for someone else's upgrade

```
messageActionStarGift#f24de7fa flags:# name_hidden:flags.0?true saved:flags.2?true converted:flags.3?true upgraded:flags.5?true refunded:flags.9?true can_upgrade:flags.10?true prepaid_upgrade:flags.13?true upgrade_separate:flags.16?true gift:StarGift message:flags.1?TextWithEntities convert_stars:flags.4?long upgrade_msg_id:flags.5?int upgrade_stars:flags.8?long from_id:flags.11?Peer peer:flags.12?Peer saved_id:flags.12?long prepaid_upgrade_hash:flags.14?string gift_msg_id:flags.15?int = MessageAction;

inputInvoiceStarGiftPrepaidUpgrade#9a0b48b8 peer:InputPeer hash:string = InputInvoice;

messageActionStarGiftUnique#34f762f3 flags:# upgrade:flags.0?true transferred:flags.1?true saved:flags.2?true refunded:flags.5?true prepaid_upgrade:flags.11?true gift:StarGift can_export_at:flags.3?int transfer_stars:flags.4?long from_id:flags.6?Peer peer:flags.7?Peer saved_id:flags.7?long resale_amount:flags.8?StarsAmount can_transfer_at:flags.9?int can_resell_at:flags.10?int = MessageAction;
```

When sending a gift, the sender can pay for the upgrade by setting inputInvoiceStarGift.include_upgrade when buying the gift.
The resulting messageActionStarGift will have the prepaid_upgrade flag set, and the associated savedStarGift will have the upgrade_stars flag set and populated with the amount paid.

It's also possible to pay to upgrade someone else's gift (even if the currently logged in user did not send them that gift) after the fact, by using inputInvoiceStarGiftPrepaidUpgrade, passing the peer where the gift was sent and the upgrade hash from messageActionStarGift.prepaid_upgrade_hash or savedStarGift.prepaid_upgrade_hash.

Then, follow the usual payment flow ».

Upon completion, a new messageActionStarGift will be emitted with the upgrade_separate flag set, and the gift_msg_id flag populated with the ID of the messageActionStarGift with the upgraded gift only valid for the receiver of the message.

#### Sharing and getting info about a collectible gift

```
starGiftUnique#1befe865 flags:# require_premium:flags.6?true resale_ton_only:flags.7?true theme_available:flags.9?true id:long gift_id:long title:string slug:string num:int owner_id:flags.0?Peer owner_name:flags.1?string owner_address:flags.2?string attributes:Vector<StarGiftAttribute> availability_issued:int availability_total:int gift_address:flags.3?string resell_amount:flags.4?Vector<StarsAmount> released_by:flags.5?Peer value_amount:flags.8?long value_currency:flags.8?string theme_peer:flags.10?Peer = StarGift;

payments.uniqueStarGift#416c56e8 gift:StarGift chats:Vector<Chat> users:Vector<User> = payments.UniqueStarGift;

payments.uniqueStarGiftValueInfo#512fe446 flags:# last_sale_on_fragment:flags.1?true value_is_average:flags.6?true currency:string value:long initial_sale_date:int initial_sale_stars:long initial_sale_price:long last_sale_date:flags.0?int last_sale_price:flags.0?long floor_price:flags.2?long average_price:flags.3?long listed_count:flags.4?int fragment_listed_count:flags.5?int fragment_listed_url:flags.5?string = payments.UniqueStarGiftValueInfo;

---functions---

payments.getUniqueStarGift#a1974d72 slug:string = payments.UniqueStarGift;
payments.getUniqueStarGiftValueInfo#4365af6b slug:string = payments.UniqueStarGiftValueInfo;
```

Info about a unique gift may be shared by creating a collectible gift link » using the slug in starGiftUnique.slug.

When parsing a received collectible gift link, invoke payments.getUniqueStarGift to obtain info about the gift.

The slug is also used when buying a gift currently on resale ».

The slug of an owned collectible gift link may also be used in any place in the API where an InputSavedStarGift is accepted, passing an inputSavedStarGiftSlug.

payments.getUniqueStarGiftValueInfo may also be used to obtain info about the value of a collectible gift.

#### Reselling collectible gifts

```
messageActionStarGiftUnique#34f762f3 flags:# upgrade:flags.0?true transferred:flags.1?true saved:flags.2?true refunded:flags.5?true prepaid_upgrade:flags.11?true gift:StarGift can_export_at:flags.3?int transfer_stars:flags.4?long from_id:flags.6?Peer peer:flags.7?Peer saved_id:flags.7?long resale_amount:flags.8?StarsAmount can_transfer_at:flags.9?int can_resell_at:flags.10?int = MessageAction;

inputSavedStarGiftUser#69279795 msg_id:int = InputSavedStarGift;
inputSavedStarGiftChat#f101aa7f peer:InputPeer saved_id:long = InputSavedStarGift;
inputSavedStarGiftSlug#2085c238 slug:string = InputSavedStarGift;

payments.resaleStarGifts#947a12df flags:# count:int gifts:Vector<StarGift> next_offset:flags.0?string attributes:flags.1?Vector<StarGiftAttribute> attributes_hash:flags.1?long chats:Vector<Chat> counters:flags.2?Vector<StarGiftAttributeCounter> users:Vector<User> = payments.ResaleStarGifts;

---functions---

payments.updateStarGiftPrice#edbe6ccb stargift:InputSavedStarGift resell_amount:StarsAmount = Updates;

payments.getResaleStarGifts#7a5fa236 flags:# sort_by_price:flags.1?true sort_by_num:flags.2?true attributes_hash:flags.0?long gift_id:long attributes:flags.3?Vector<StarGiftAttributeId> offset:string limit:int = payments.ResaleStarGifts;
```

An owned collectible gift » can be put up for sale on the gift marketplace » by using payments.updateStarGiftPrice, specifying the price in resell_stars.

Note that if the messageActionStarGiftUnique/savedStarGift.can_resell_at flag is set, the gift can be put up for sale only starting from the specified date.

The minimum and maximum resale prices are specified in the stars_stargift_resale_amount_min »/stars_stargift_resale_amount_max » client configuration parameters; passing 0 will unlist the gift from the marketplace.
If someone buys the gift, you will get price*stars_stargift_resale_commission_permille » /1000 stars.

When specifying the price in nanotons, the minimum and maximum resale prices are specified in the ton_stargift_resale_amount_min »/ton_stargift_resale_amount_max » client configuration parameters; passing 0 will unlist the gift from the marketplace.
If someone buys the gift, you will get price*ton_stargift_resale_commission_permille » /1000 nanoton.

Use payments.getStarGifts to obtain the full list of available starGifts; this method may return some sold-out gifts that have the availability_resale flag set, which indicates that some gifts of this type are on resale », use payments.getResaleStarGifts to fetch them.

See here » for detailed documentation on the payments.getResaleStarGifts method.

To buy a gift on resale, follow the usual payment flow », passing an inputInvoiceStarGiftResale.

#### Transferring collectible gifts

```
messageActionStarGiftUnique#34f762f3 flags:# upgrade:flags.0?true transferred:flags.1?true saved:flags.2?true refunded:flags.5?true prepaid_upgrade:flags.11?true gift:StarGift can_export_at:flags.3?int transfer_stars:flags.4?long from_id:flags.6?Peer peer:flags.7?Peer saved_id:flags.7?long resale_amount:flags.8?StarsAmount can_transfer_at:flags.9?int can_resell_at:flags.10?int = MessageAction;

starGiftUnique#1befe865 flags:# require_premium:flags.6?true resale_ton_only:flags.7?true theme_available:flags.9?true id:long gift_id:long title:string slug:string num:int owner_id:flags.0?Peer owner_name:flags.1?string owner_address:flags.2?string attributes:Vector<StarGiftAttribute> availability_issued:int availability_total:int gift_address:flags.3?string resell_amount:flags.4?Vector<StarsAmount> released_by:flags.5?Peer value_amount:flags.8?long value_currency:flags.8?string theme_peer:flags.10?Peer = StarGift;

inputSavedStarGiftUser#69279795 msg_id:int = InputSavedStarGift;
inputSavedStarGiftChat#f101aa7f peer:InputPeer saved_id:long = InputSavedStarGift;
inputSavedStarGiftSlug#2085c238 slug:string = InputSavedStarGift;

inputInvoiceStarGiftTransfer#4a5f5bd9 stargift:InputSavedStarGift to_id:InputPeer = InputInvoice;

---functions---

payments.transferStarGift#7f18176a stargift:InputSavedStarGift to_id:InputPeer = Updates;
```

A collectible gift may be transferred to another user.

To transfer a collectible gift, pay messageActionStarGiftUnique/savedStarGift.transfer_stars Telegram Stars by invoking payments.getPaymentForm, passing an inputInvoiceStarGiftTransfer with the following parameters:

- stargift: The identifier of the received gift

- to_id: The destination peer

Then, follow the usual payment flow ».

If messageActionStarGiftUnique/savedStarGift.transfer_stars is not set, the gift may be transferred for free: in this case, simply invoke payments.transferStarGift.

#### Withdraw a collectible gift to the TON blockchain

```
messageActionStarGiftUnique#34f762f3 flags:# upgrade:flags.0?true transferred:flags.1?true saved:flags.2?true refunded:flags.5?true prepaid_upgrade:flags.11?true gift:StarGift can_export_at:flags.3?int transfer_stars:flags.4?long from_id:flags.6?Peer peer:flags.7?Peer saved_id:flags.7?long resale_amount:flags.8?StarsAmount can_transfer_at:flags.9?int can_resell_at:flags.10?int = MessageAction;

savedStarGift#19a9b572 flags:# name_hidden:flags.0?true unsaved:flags.5?true refunded:flags.9?true can_upgrade:flags.10?true pinned_to_top:flags.12?true upgrade_separate:flags.17?true from_id:flags.1?Peer date:int gift:StarGift message:flags.2?TextWithEntities msg_id:flags.3?int saved_id:flags.11?long convert_stars:flags.4?long upgrade_stars:flags.6?long can_export_at:flags.7?int transfer_stars:flags.8?long can_transfer_at:flags.13?int can_resell_at:flags.14?int collection_id:flags.15?Vector<int> prepaid_upgrade_hash:flags.16?string = SavedStarGift;

payments.starGiftWithdrawalUrl#84aa3a9c url:string = payments.StarGiftWithdrawalUrl;

---functions---

payments.getStarGiftWithdrawalUrl#d06e93a8 stargift:InputSavedStarGift password:InputCheckPasswordSRP = payments.StarGiftWithdrawalUrl;
```

A collectible gift can be converted to an NFT on the TON blockchain by using payments.getStarGiftWithdrawalUrl: the method requires the current user's 2FA password, passed as specified here », and it returns a URL that can be used to import the NFT on Fragment.

Note that if the messageActionStarGiftUnique/savedStarGift.can_export_at flag is set, the gift can be exported to the blockchain only starting from the specified date.

#### Setting a collectible gift as emoji status

Owned collectible gifts » may be set as emoji statuses: see here » for more info on the full flow.

#### Setting a collectible gift as chat theme

Some owned collectible gifts » (those with the starGiftUnique.theme_available flag set) may be set as chat themes: see here » for more info on the full flow.

