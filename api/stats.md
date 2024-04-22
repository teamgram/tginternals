# Channel statistics

Telegram offers detailed channel statistics for channels and supergroups.

### Channel statistics

Schema:

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

- Graphs: graphs are described below ».

### Supergroup statistics

Schema:

Administrators of supergroups of a certain size (the exact limit is a server-side config, returned in the can_view_stats flag of channelFull) can call stats.getMegagroupStats to get detailed supergroup statistics.
The query must be sent to the datacenter with ID channelFull.stats_dc, obtainable using channels.getFullChannel.
The returned stats.broadcastStats contains multiple statistics, see the constructor page for more info ».

### Message statistics

Administrators of channels of a certain size (the exact limit is a server-side config, returned in the can_view_stats flag of channelFull) can invoke stats.getMessageStats to get statistics of a specific message.
The query must be sent to the datacenter with ID channelFull.stats_dc, obtainable using channels.getFullChannel.
The returned stats.messageStats contains the view graph of the message.

stats.getMessagePublicForwards may also be used to obtain a list of messages, indicating to which other public channels was a channel message forwarded: it will return a list of messages with peer_id equal to the public channel to which this message was forwarded.

### Story statistics

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

Certain graphs are not directly sent in the stats.broadcastStats constructor to reduce server load: instead, those graphs will be sent as a statsGraphAsync constructor, and should be fetched separately using stats.loadAsyncGraph.

After obtaining the full statsGraph constructor, clients should parse the JSON graph object in the json field.

Object structure:

The following chart restrictions apply:

- Up to 50 columns on one graph must be supported.

- Chart types are always the same for every column in the graph.

- The bar chart type and stacked option are always used together.

- percentage is always used with the area graph.

### Chart zooming

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

The color key can be one of red, lightblue, lightgreen, golden, green, orange, blue, indigo.
Apps can choose to use a color value specified by the currently loaded theme: for example, the android app uses statisticChartLine_* themekeys for each of the color keys, check out the assets directory for a bunch of default themes with various colors for channel statistics.

However, the server may also choose to return just a plain color value in hex format:

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

