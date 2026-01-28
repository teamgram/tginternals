# Channel statistics

Telegram offers detailed channel statistics for channels and supergroups.

### Channel statistics

Schema:

```
statsDateRangeDays#b637edaf min_date:int max_date:int = StatsDateRangeDays;

statsAbsValueAndPrev#cb43acde current:double previous:double = StatsAbsValueAndPrev;

statsPercentValue#cbce2fe0 part:double total:double = StatsPercentValue;

statsGraphAsync#4a27eb2d token:string = StatsGraph;
statsGraphError#bedc9822 error:string = StatsGraph;
statsGraph#8ea464b6 flags:# json:DataJSON zoom_token:flags.0?string = StatsGraph;

postInteractionCountersMessage#e7058e7f msg_id:int views:int forwards:int reactions:int = PostInteractionCounters;
postInteractionCountersStory#8a480e27 story_id:int views:int forwards:int reactions:int = PostInteractionCounters;

stats.broadcastStats#396ca5fc period:StatsDateRangeDays followers:StatsAbsValueAndPrev views_per_post:StatsAbsValueAndPrev shares_per_post:StatsAbsValueAndPrev reactions_per_post:StatsAbsValueAndPrev views_per_story:StatsAbsValueAndPrev shares_per_story:StatsAbsValueAndPrev reactions_per_story:StatsAbsValueAndPrev enabled_notifications:StatsPercentValue growth_graph:StatsGraph followers_graph:StatsGraph mute_graph:StatsGraph top_hours_graph:StatsGraph interactions_graph:StatsGraph iv_interactions_graph:StatsGraph views_by_source_graph:StatsGraph new_followers_by_source_graph:StatsGraph languages_graph:StatsGraph reactions_by_emotion_graph:StatsGraph story_interactions_graph:StatsGraph story_reactions_by_emotion_graph:StatsGraph recent_posts_interactions:Vector<PostInteractionCounters> = stats.BroadcastStats;

messages.chatFull#e5d7d19c full_chat:ChatFull chats:Vector<Chat> users:Vector<User> = messages.ChatFull;
channelFull#e4e0b29d flags:# can_view_participants:flags.3?true can_set_username:flags.6?true can_set_stickers:flags.7?true hidden_prehistory:flags.10?true can_set_location:flags.16?true has_scheduled:flags.19?true can_view_stats:flags.20?true blocked:flags.22?true flags2:# can_delete_channel:flags2.0?true antispam:flags2.1?true participants_hidden:flags2.2?true translations_disabled:flags2.3?true stories_pinned_available:flags2.5?true view_forum_as_messages:flags2.6?true restricted_sponsored:flags2.11?true can_view_revenue:flags2.12?true paid_media_allowed:flags2.14?true can_view_stars_revenue:flags2.15?true paid_reactions_available:flags2.16?true stargifts_available:flags2.19?true paid_messages_available:flags2.20?true id:long about:string participants_count:flags.0?int admins_count:flags.1?int kicked_count:flags.2?int banned_count:flags.2?int online_count:flags.13?int read_inbox_max_id:int read_outbox_max_id:int unread_count:int chat_photo:Photo notify_settings:PeerNotifySettings exported_invite:flags.23?ExportedChatInvite bot_info:Vector<BotInfo> migrated_from_chat_id:flags.4?long migrated_from_max_id:flags.4?int pinned_msg_id:flags.5?int stickerset:flags.8?StickerSet available_min_id:flags.9?int folder_id:flags.11?int linked_chat_id:flags.14?long location:flags.15?ChannelLocation slowmode_seconds:flags.17?int slowmode_next_send_date:flags.18?int stats_dc:flags.12?int pts:int call:flags.21?InputGroupCall ttl_period:flags.24?int pending_suggestions:flags.25?Vector<string> groupcall_default_join_as:flags.26?Peer theme_emoticon:flags.27?string requests_pending:flags.28?int recent_requesters:flags.28?Vector<long> default_send_as:flags.29?Peer available_reactions:flags.30?ChatReactions reactions_limit:flags2.13?int stories:flags2.4?PeerStories wallpaper:flags2.7?WallPaper boosts_applied:flags2.8?int boosts_unrestrict:flags2.9?int emojiset:flags2.10?StickerSet bot_verification:flags2.17?BotVerification stargifts_count:flags2.18?int send_paid_messages_stars:flags2.21?long main_tab:flags2.22?ProfileTab = ChatFull;

---functions---

stats.getBroadcastStats#ab42441a flags:# dark:flags.0?true channel:InputChannel = stats.BroadcastStats;
stats.loadAsyncGraph#621d5fa0 flags:# token:string x:flags.0?long = StatsGraph;

channels.getFullChannel#8736a09 channel:InputChannel = messages.ChatFull;
```

Administrators of channels of a certain size (the exact limit is a server-side config, returned in the can_view_stats flag of channelFull) can invoke stats.getBroadcastStats to get detailed channel statistics.
The query must be sent to the datacenter with ID channelFull.stats_dc, obtainable using channels.getFullChannel.
The returned stats.broadcastStats contains multiple statistics:

- Period-related statistics: a pair of values, one at the beginning and one at the end of the period in consideration (period).   The period typically depends on channel activity.

- Absolute follower count (followers)

- total_viewcount/postcount, for posts posted during the period in consideration (views_per_post).

- Note that in this case, current refers to the period in consideration (min_date till max_date), and prev refers to the previous period ((min_date - (max_date - min_date)) till min_date).

- total_sharecount/postcount, for posts posted during the period in consideration (shares_per_post).

- Note that in this case, current refers to the period in consideration (min_date till max_date), and prev refers to the previous period ((min_date - (max_date - min_date)) till min_date).

- Percentage statistics

- Percentage of subscribers with enabled notifications (enabled_notifications)

- Graphs: graphs are described below ».

### Supergroup statistics

Schema:

```
statsGroupTopPoster#9d04af9b user_id:long messages:int avg_chars:int = StatsGroupTopPoster;
statsGroupTopInviter#535f779d user_id:long invitations:int = StatsGroupTopInviter;
statsGroupTopAdmin#d7584c87 user_id:long deleted:int kicked:int banned:int = StatsGroupTopAdmin;

stats.megagroupStats#ef7ff916 period:StatsDateRangeDays members:StatsAbsValueAndPrev messages:StatsAbsValueAndPrev viewers:StatsAbsValueAndPrev posters:StatsAbsValueAndPrev growth_graph:StatsGraph members_graph:StatsGraph new_members_by_source_graph:StatsGraph languages_graph:StatsGraph messages_graph:StatsGraph actions_graph:StatsGraph top_hours_graph:StatsGraph weekdays_graph:StatsGraph top_posters:Vector<StatsGroupTopPoster> top_admins:Vector<StatsGroupTopAdmin> top_inviters:Vector<StatsGroupTopInviter> users:Vector<User> = stats.MegagroupStats;

messages.chatFull#e5d7d19c full_chat:ChatFull chats:Vector<Chat> users:Vector<User> = messages.ChatFull;
channelFull#e4e0b29d flags:# can_view_participants:flags.3?true can_set_username:flags.6?true can_set_stickers:flags.7?true hidden_prehistory:flags.10?true can_set_location:flags.16?true has_scheduled:flags.19?true can_view_stats:flags.20?true blocked:flags.22?true flags2:# can_delete_channel:flags2.0?true antispam:flags2.1?true participants_hidden:flags2.2?true translations_disabled:flags2.3?true stories_pinned_available:flags2.5?true view_forum_as_messages:flags2.6?true restricted_sponsored:flags2.11?true can_view_revenue:flags2.12?true paid_media_allowed:flags2.14?true can_view_stars_revenue:flags2.15?true paid_reactions_available:flags2.16?true stargifts_available:flags2.19?true paid_messages_available:flags2.20?true id:long about:string participants_count:flags.0?int admins_count:flags.1?int kicked_count:flags.2?int banned_count:flags.2?int online_count:flags.13?int read_inbox_max_id:int read_outbox_max_id:int unread_count:int chat_photo:Photo notify_settings:PeerNotifySettings exported_invite:flags.23?ExportedChatInvite bot_info:Vector<BotInfo> migrated_from_chat_id:flags.4?long migrated_from_max_id:flags.4?int pinned_msg_id:flags.5?int stickerset:flags.8?StickerSet available_min_id:flags.9?int folder_id:flags.11?int linked_chat_id:flags.14?long location:flags.15?ChannelLocation slowmode_seconds:flags.17?int slowmode_next_send_date:flags.18?int stats_dc:flags.12?int pts:int call:flags.21?InputGroupCall ttl_period:flags.24?int pending_suggestions:flags.25?Vector<string> groupcall_default_join_as:flags.26?Peer theme_emoticon:flags.27?string requests_pending:flags.28?int recent_requesters:flags.28?Vector<long> default_send_as:flags.29?Peer available_reactions:flags.30?ChatReactions reactions_limit:flags2.13?int stories:flags2.4?PeerStories wallpaper:flags2.7?WallPaper boosts_applied:flags2.8?int boosts_unrestrict:flags2.9?int emojiset:flags2.10?StickerSet bot_verification:flags2.17?BotVerification stargifts_count:flags2.18?int send_paid_messages_stars:flags2.21?long main_tab:flags2.22?ProfileTab = ChatFull;

---functions---

stats.getMegagroupStats#dcdf8607 flags:# dark:flags.0?true channel:InputChannel = stats.MegagroupStats;

channels.getFullChannel#8736a09 channel:InputChannel = messages.ChatFull;
```

Administrators of supergroups of a certain size (the exact limit is a server-side config, returned in the can_view_stats flag of channelFull) can call stats.getMegagroupStats to get detailed supergroup statistics.
The query must be sent to the datacenter with ID channelFull.stats_dc, obtainable using channels.getFullChannel.
The returned stats.broadcastStats contains multiple statistics, see the constructor page for more info ».

### Message statistics

```
stats.messageStats#7fe91c14 views_graph:StatsGraph reactions_by_emotion_graph:StatsGraph = stats.MessageStats;

messages.chatFull#e5d7d19c full_chat:ChatFull chats:Vector<Chat> users:Vector<User> = messages.ChatFull;
channelFull#e4e0b29d flags:# can_view_participants:flags.3?true can_set_username:flags.6?true can_set_stickers:flags.7?true hidden_prehistory:flags.10?true can_set_location:flags.16?true has_scheduled:flags.19?true can_view_stats:flags.20?true blocked:flags.22?true flags2:# can_delete_channel:flags2.0?true antispam:flags2.1?true participants_hidden:flags2.2?true translations_disabled:flags2.3?true stories_pinned_available:flags2.5?true view_forum_as_messages:flags2.6?true restricted_sponsored:flags2.11?true can_view_revenue:flags2.12?true paid_media_allowed:flags2.14?true can_view_stars_revenue:flags2.15?true paid_reactions_available:flags2.16?true stargifts_available:flags2.19?true paid_messages_available:flags2.20?true id:long about:string participants_count:flags.0?int admins_count:flags.1?int kicked_count:flags.2?int banned_count:flags.2?int online_count:flags.13?int read_inbox_max_id:int read_outbox_max_id:int unread_count:int chat_photo:Photo notify_settings:PeerNotifySettings exported_invite:flags.23?ExportedChatInvite bot_info:Vector<BotInfo> migrated_from_chat_id:flags.4?long migrated_from_max_id:flags.4?int pinned_msg_id:flags.5?int stickerset:flags.8?StickerSet available_min_id:flags.9?int folder_id:flags.11?int linked_chat_id:flags.14?long location:flags.15?ChannelLocation slowmode_seconds:flags.17?int slowmode_next_send_date:flags.18?int stats_dc:flags.12?int pts:int call:flags.21?InputGroupCall ttl_period:flags.24?int pending_suggestions:flags.25?Vector<string> groupcall_default_join_as:flags.26?Peer theme_emoticon:flags.27?string requests_pending:flags.28?int recent_requesters:flags.28?Vector<long> default_send_as:flags.29?Peer available_reactions:flags.30?ChatReactions reactions_limit:flags2.13?int stories:flags2.4?PeerStories wallpaper:flags2.7?WallPaper boosts_applied:flags2.8?int boosts_unrestrict:flags2.9?int emojiset:flags2.10?StickerSet bot_verification:flags2.17?BotVerification stargifts_count:flags2.18?int send_paid_messages_stars:flags2.21?long main_tab:flags2.22?ProfileTab = ChatFull;

---functions---

stats.getMessageStats#b6e0a3f5 flags:# dark:flags.0?true channel:InputChannel msg_id:int = stats.MessageStats;

channels.getFullChannel#8736a09 channel:InputChannel = messages.ChatFull;

stats.getMessagePublicForwards#5f150144 channel:InputChannel msg_id:int offset:string limit:int = stats.PublicForwards;
```

Administrators of channels of a certain size (the exact limit is a server-side config, returned in the can_view_stats flag of channelFull) can invoke stats.getMessageStats to get statistics of a specific message.
The query must be sent to the datacenter with ID channelFull.stats_dc, obtainable using channels.getFullChannel.
The returned stats.messageStats contains the view graph of the message.

stats.getMessagePublicForwards may also be used to obtain a list of messages, indicating to which other public channels was a channel message forwarded: it will return a list of messages with peer_id equal to the public channel to which this message was forwarded.

### Story statistics

```
stats.storyStats#50cd067c views_graph:StatsGraph reactions_by_emotion_graph:StatsGraph = stats.StoryStats;

publicForwardMessage#1f2bf4a message:Message = PublicForward;
publicForwardStory#edf3add0 peer:Peer story:StoryItem = PublicForward;

stats.publicForwards#93037e20 flags:# count:int forwards:Vector<PublicForward> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = stats.PublicForwards;

---functions---

stats.getStoryStats#374fef40 flags:# dark:flags.0?true peer:InputPeer id:int = stats.StoryStats;

stats.getStoryPublicForwards#a6437ef6 peer:InputPeer id:int offset:string limit:int = stats.PublicForwards;
```

Use stats.getStoryStats to obtain statistics about a story.

Use stats.getStoryPublicForwards to obtain forwards of a story as a message to public chats and reposts by public channels.

There are four available visualizations for graph types:

- Line graph

- Step graph

- Bar graph

- Area graph

Graph modifiers (see various graphs for examples):

- y_scaled - Indicates that each of the two (!) lines in a step graph must be visualized on its own scale, with two different tick axes on the left and right parts of the graph

- percentage - Indicates whether value percentages should be shown in labels

- stacked - Depending on the graph type, indicates stacking of multiple columns in the same graph

### Graph syntax

```
statsGraphAsync#4a27eb2d token:string = StatsGraph;
statsGraphError#bedc9822 error:string = StatsGraph;
statsGraph#8ea464b6 flags:# json:DataJSON zoom_token:flags.0?string = StatsGraph;

dataJSON#7d748d04 data:string = DataJSON;

---functions---

stats.loadAsyncGraph#621d5fa0 flags:# token:string x:flags.0?long = StatsGraph;
```

Certain graphs are not directly sent in the stats.broadcastStats constructor to reduce server load: instead, those graphs will be sent as a statsGraphAsync constructor, and should be fetched separately using stats.loadAsyncGraph.

After obtaining the full statsGraph constructor, clients should parse the JSON graph object in the json field.

Object structure:

The following chart restrictions apply:

- Up to 50 columns on one graph must be supported.

- Chart types are always the same for every column in the graph.

- The bar chart type and stacked option are always used together.

- percentage is always used with the area graph.

### Chart zooming

```
statsGraphError#bedc9822 error:string = StatsGraph;
statsGraph#8ea464b6 flags:# json:DataJSON zoom_token:flags.0?string = StatsGraph;

dataJSON#7d748d04 data:string = DataJSON;

---functions---

stats.loadAsyncGraph#621d5fa0 flags:# token:string x:flags.0?long = StatsGraph;
```

Graphs that support zooming will contain a zoom_token in the statsGraph constructor.
Said token should be then used as token in a new stats.loadAsyncGraph call triggered when the user clicks on the label, related to a certain x axis in the graph (see graph examples).
The x coordinate of the label should be provided to the x parameter; the method will then return (if available) a more detailed subgraph.
If not enough data is available, a localized statsGraphError will be returned.

Typical zoom visualization rules:

- Any percentage graph (even if a zoom_token is not available) => pie chart

- line graph => line graph

- step graph => step graph

- bar graph => bar graph

- area graph => area graph

### Chart colors

Chart colors can be provided as a color key, followed by the primary color value in hex format:

```
red#e05356
```

The color key can be one of red, lightblue, lightgreen, golden, green, orange, blue, indigo.
Apps can choose to use a color value specified by the currently loaded theme: for example, the android app uses statisticChartLine_* themekeys for each of the color keys, check out the assets directory for a bunch of default themes with various colors for channel statistics.

However, the server may also choose to return just a plain color value in hex format:

```
#e05356
```

In this case, the dark flag of the stats.getBroadcastStats method can be used to choose the palette of returned colors.

### Line graph

Simple single line graph

### Step graph

Step graph, always "stacked" (to indicate multiple lines)

### Bar graph

Bar graph with multiple lines, always "stacked" (to indicate actual stacked bars, biggest bars first)

### Area graph

Mixed bar/line graph, always "stacked" (to indicate actual stacked bars, biggest bars first)

### Piechart

Pie chart, typically obtained only when zooming into percentage graphs

