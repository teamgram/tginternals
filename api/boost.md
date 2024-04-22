# Channel boosts
Telegram Premium users can grant their favorite channels additional features like the ability to post stories by giving them boosts.
Channels level up as they gain more boosts – and for each level, they gain additional features.
Additionally, channel admins may gain even more boosts by starting giveaways ».
The maximum possible boost level for a channel is specified in the boosts_channel_level_max config key.
Schema:
Each user has a certain number of boost slots that can be assigned to channels: the precise number depends on whether they bought or were gifted a Premium subscription, and can be fetched using premium.getMyBoosts, along with info about the channels currently occupying each slot, if any.
Gifting a Telegram Premium subscription to another user will create boosts_per_sent_gift new boost slots for us, and one boost slot for the destination user.
Use premium.applyBoost to assign some of your boost slots to a channel.
A PREMIUM_ACCOUNT_REQUIRED error will be returned if the current account does not have a Telegram Premium subscription.
A BOOST_NOT_MODIFIED RPC error will be returned when calling any of the two methods if the user is already boosting the specified channel with the same slots.
After assigning a slot a channel, the user may not change the boosted channel for that slot for a certain cooldown period, specified in the myBoost.cooldown_until_date field: if the cooldown period isn't over yet, the method will return a 420 FLOOD_WAIT_X error, indicating the number of seconds left before a different channel can be boosted.
Users may also invoke premium.getBoostsStatus, to get the current boost status of a channel as a premium.boostsStatus constructor, check out the constructor page for more info.
Channel administrators may invoke premium.getBoostsList to fetch the list of users currently boosting the channel, and premium.getUserBoosts to get info about the boosts sent to a channel by a specific user.
### Features
#### Posting stories as a channel
With each boost, channels can post 1 additional story per day to their subscribers' story feeds.
Everything works exactly the same as when posting stories as a user, with the only difference that clients should pass the appropriate inputPeerChannel instead of inputPeerSelf to stories.canSendStory, stories.sendStory and all the other story methods, see the main documentation » for more info.
Use stories.getChatsToSend to obtain a list of channels where the user can post stories; stories.canSendStory must still be used before uploading a story to make sure no other limit was reached, as described in the main documentation ».
#### Changing message accent color
After reaching at least the boost level specified in the channel_min_level field of the help.peerColorOption constructor for the chosen palette, channels gain the ability to change their message accent palette ».
#### Changing message accent emoji
After reaching at least the boost level specified in the channel_bg_icon_level_min config parameter, channels gain the ability to change the emoji used in the message accent palette ».
#### Changing profile accent color/emoji
After reaching at least the boost level specified in the channel_profile_bg_icon_level_min config parameter and the boost level specified in the channel_min_level field of the help.peerColorOption constructor for the chosen palette, channels gain the ability to change the emoji and color used in the profile accent palette ».
#### Setting wallpapers
After reaching at least the boost level specified in the channel_wallpaper_level_min config parameter, channels gain the ability to set a fill channel wallpaper, see here » for more info.
After reaching at least the boost level specified in the channel_custom_wallpaper_level_min config parameter, channels gain the ability to set any custom wallpaper, not just fill channel wallpapers, see here » for more info.
#### Setting a custom emoji status
After reaching at least the boost level specified in the channel_emoji_status_level_min config parameter, channels gain the ability to change their status emoji ».
