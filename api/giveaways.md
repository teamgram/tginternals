# Giveaways
Telegram channel administrators may launch giveaways to randomly distribute Telegram Premium subscriptions and other gifts among their followers, in exchange for boosts.
This functionality should only be enabled if the giveaway_gifts_purchase_available config value is set to true.
Note that the flow described below can also be used to gift a Premium subscriptions to multiple friends, and is different from the old gift flow, which allowed gifting only one subscription with some extra limitations, not present in this flow.
Note that premium multigift links lead to a page that uses the new gift flow described below.
Schema:
First of all, invoke payments.getPremiumGiftCodeOptions to obtain a list of premiumGiftCodeOption constructors, containing a list of giveaway options that may be chosen by the admin, indicating the number and duration of the of Telegram Premium subscriptions that will be gifted in the giveaway, along with their price (amount) in the specified currency (see the constructor page » for more info on these fields).
Once the admin has chosen a specific gift code option, invoke payments.getPaymentForm, passing an inputInvoicePremiumGiftCode, with the chosen premiumGiftCodeOption in option and a purpose containing either:
- inputStorePaymentPremiumGiveaway to create a giveaway, where Telegram will randomly select option.users subscribers to the channel specified in purpose.boost_peer (only new subscribers starting from the giveaway creation date if the purpose.only_new_subscribers field is set).
- Additional channels that the user must join to participate to the giveaway can be specified in additional_peers.
- The set of users that can participate to the giveaway can be restricted by passing an explicit whitelist of up to giveaway_countries_max countries, specified as two-letter ISO 3166-1 alpha-2 country codes in countries_iso2.
- The end date of the giveaway must be specified in until_date, and it must be at most giveaway_period_max seconds in the future; at that date, Telegram will randomly choose option.users subscribers according to the conditions specified above, and send them a Telegram Premium giftcode as a messageActionGiftCode constructor, that should be used client-side to generate a giftcode link.
- The channel specified in boost_peer will receive giveaway_boosts_per_premium boosts from each user, that cannot be reassigned to another channel for the duration of the gifted subscription.
- or inputStorePaymentPremiumGiftCode, to gift Telegram Premium subscriptions only to some specific subscribers (purpose.users, max giveaway_add_peers_max users) of the channel specified in purpose.boost_peer, which will receive giveaway_boosts_per_premium boosts from each user, that cannot be reassigned to another channel for the duration of the gifted subscription.
- Users may also use this method to simply gift subscriptions to contacts by not setting the boost_peer field: in this case, gifting a Telegram Premium subscription to another user will create boosts_per_sent_gift boost slots » for us, and one boost slot for the destination user.
Then, follow the invoice payment flow as described in the payments documentation ».
More alternative payment flows are also available:
- The Premium Bot flow, by contacting premium_bot_username, and following the inline keyboard payment flow for giveaways (the final keyboard with the prices will contain buttons with invoice deep links » that should be used to make the payment).
- Payment via Fragment, which also allows making larger purchases.
- The store-based subscription flow based on payments.assignAppStoreTransaction/payments.assignPlayMarketTransaction, currently not available to third-party apps.
Then:
- If the payment was made using the payments.getPaymentForm or payments.assignAppStoreTransaction/payments.assignPlayMarketTransaction payment flows, the giveaway will launch as soon as the payment is complete.
- Otherwise, if the Premium bot or Fragment flows were used, once the payment for the giveaway is made, invoke premium.getBoostsStatus, passing to peer the ID of the channel that we selected when paying for the giveaway, to obtain a prepaidGiveaway constructor in premium.boostsStatus.prepaid_giveaways, containing info about the prepaid giveaway.
- To actually launch the giveaway for the Fragment and bot flows, invoke payments.launchPrepaidGiveaway, passing prepaidGiveaway.id to giveaway_id, the ID of the channel to peer and giveaway settings in purpose (populated as specified above).
Finally:
- If the payment succeeds and we're launching a giveaway using inputStorePaymentPremiumGiveaway: a messageActionGiveawayLaunch service message and a media message containing a messageMediaGiveaway will be sent to the channel.
- Once the giveaway is over, a messageActionGiveawayResults will be sent to the channel and the winners will automatically receive a messageActionGiftCode service message from Telegram's service user, containing the slug that can be used to generate a giftcode link to redeem the Premium subscription.
- The messageActionGiftCode.via_giveaway flag will be set.
- If the payment succeeds and we're simply gifting some subscriptions to specific users inputStorePaymentPremiumGiftCode: the specified users will automatically receive a messageActionGiftCode service message from Telegram's service user, containing the slug that can be used to generate a giftcode link to redeem the Premium subscription.
- The messageActionGiftCode.via_giveaway flag will not be set.
- Note that if the payment was made on behalf of the user (i.e. if boost_peer was not set), then the users to which the gift was sent will instead receive a messageService from the user that sent the gift, containing a messageActionGiftPremium constructor with further info about the price and duration of the gifted Telegram Premium subscription.
- Clients should display this message, along with a sticker from the inputStickerSetPremiumGifts stickerset: here's an example.
The messageActionGiftCode.slug should be used to generate a giftcode link, that the user can use to redeem the subscription, or re-gift it to someone else.
If winners_are_visible flag is set while starting a giveaway, giveaway winners are public and will be listed in a messageMediaGiveawayResults message that will be automatically sent to the channel once the giveaway ends.
Any user can invoke payments.checkGiftCode with the link's slug to obtain info about the giveaway, such as the channel that gifted the subscription (from_id), and the user that originally received the gift (to_id).
This can also be useful to channel administrators to precisely determine the winners of a giveaway, for example if the giveaway also included some extra gifts apart from Premium subscriptions (like Teslas): the winners can simply send their link as undisputable proof that they won the giveaway, because the user that received the gift can be viewed in the to_id field returned by Telegram when invoking payments.checkGiftCode on the slug.
Another way for admins to check who received the gifts is to simply use premium.getBoostsList while the boosts received by the gifts are still active.
To claim the Telegram Premium subscription, simply invoke payments.applyGiftCode, passing the link's slug.
