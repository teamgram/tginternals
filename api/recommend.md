# Similar channels and bots

The API offers a method to obtain a list of similarly themed public channels and bots, selected based on similarities in their subscriber bases.

### Similar channels

Scheme:

```
messages.chats#64ff9fd5 chats:Vector<Chat> = messages.Chats;
messages.chatsSlice#9cd81144 count:int chats:Vector<Chat> = messages.Chats;

---functions---

channels.getChannelRecommendations#25a71742 flags:# channel:flags.0?InputChannel = messages.Chats;
```

Clients should invoke channels.getChannelRecommendations after joining a channel (passing the channel's peer in channel), automatically displaying a popup with a list of similarly themed channels.

The same method should also be invoked when opening a special "Similar channels" tab in the channel's profile (similar to the Media/Links/Gifs/etc tabs).

The method should also be called without setting the channel flag in the "Similar channels" section of the "Channels" tab of global search, to return a global list of recommended channels, similar to the ones the current user has already joined, see here » for more info.

The maximum number of similar channels that can be recommended by channels.getChannelRecommendations» to Premium/non-Premium users is contained in the recommended_channels_limit_premium/recommended_channels_limit_default app configuration keys.

Non-Premium users may get a reduced result set in the form of a messages.chatsSlice where count > the number of results in chats: upgrading to a Premium account will return the full result set as a messages.chatsSlice.

### Similar bots

```
users.users#62d706b8 users:Vector<User> = users.Users;
users.usersSlice#315a4974 count:int users:Vector<User> = users.Users;

---functions---

bots.getBotRecommendations#a1b70815 bot:InputUser = users.Users;
```

The same method should also be invoked when opening a special "Similar bots" tab in the bot's profile (similar to the Media/Links/Gifs/etc tabs).

Non-Premium users may get a reduced result set in the form of a users.usersSlice where count > the number of results in users: upgrading to a Premium account will return the full result set as a users.users.

