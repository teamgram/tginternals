# Similar channels
The API offers a method to obtain a list of similarly themed public channels, selected based on similarities in their subscriber bases.
Scheme:
Clients should invoke this method after joining a channel, automatically displaying a popup with a list of similarly themed channels.
The same method should also be invoked when opening a special "Similar channels" tab in the channel's profile (similar to the Media/Links/Gifs/etc tabs).
The maximum number of similar channels that can be recommended by channels.getChannelRecommendations» to Premium/non-Premium users is contained in the recommended_channels_limit_premium/recommended_channels_limit_default app configuration keys.
