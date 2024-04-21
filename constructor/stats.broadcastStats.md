# stats.broadcastStats
Channel statistics.

```
stats.broadcastStats#396ca5fc period:StatsDateRangeDays followers:StatsAbsValueAndPrev views_per_post:StatsAbsValueAndPrev shares_per_post:StatsAbsValueAndPrev reactions_per_post:StatsAbsValueAndPrev views_per_story:StatsAbsValueAndPrev shares_per_story:StatsAbsValueAndPrev reactions_per_story:StatsAbsValueAndPrev enabled_notifications:StatsPercentValue growth_graph:StatsGraph followers_graph:StatsGraph mute_graph:StatsGraph top_hours_graph:StatsGraph interactions_graph:StatsGraph iv_interactions_graph:StatsGraph views_by_source_graph:StatsGraph new_followers_by_source_graph:StatsGraph languages_graph:StatsGraph reactions_by_emotion_graph:StatsGraph story_interactions_graph:StatsGraph story_reactions_by_emotion_graph:StatsGraph recent_posts_interactions:Vector<PostInteractionCounters> = stats.BroadcastStats;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| period | StatsDateRangeDays | Period in consideration |
| followers | StatsAbsValueAndPrev | Follower count change for period in consideration |
| views_per_post | StatsAbsValueAndPrev | total_viewcount/postcount, for posts posted during the period in consideration. Note that in this case, current refers to the period in consideration (min_date till max_date), and prev refers to the previous period ((min_date - (max_date - min_date)) till min_date). |
| shares_per_post | StatsAbsValueAndPrev | total_sharecount/postcount, for posts posted during the period in consideration. Note that in this case, current refers to the period in consideration (min_date till max_date), and prev refers to the previous period ((min_date - (max_date - min_date)) till min_date) |
| reactions_per_post | StatsAbsValueAndPrev | total_reactions/postcount, for posts posted during the period in consideration. Note that in this case, current refers to the period in consideration (min_date till max_date), and prev refers to the previous period ((min_date - (max_date - min_date)) till min_date) |
| views_per_story | StatsAbsValueAndPrev | total_views/storycount, for posts posted during the period in consideration. Note that in this case, current refers to the period in consideration (min_date till max_date), and prev refers to the previous period ((min_date - (max_date - min_date)) till min_date) |
| shares_per_story | StatsAbsValueAndPrev | total_shares/storycount, for posts posted during the period in consideration. Note that in this case, current refers to the period in consideration (min_date till max_date), and prev refers to the previous period ((min_date - (max_date - min_date)) till min_date) |
| reactions_per_story | StatsAbsValueAndPrev | total_reactions/storycount, for posts posted during the period in consideration. Note that in this case, current refers to the period in consideration (min_date till max_date), and prev refers to the previous period ((min_date - (max_date - min_date)) till min_date) |
| enabled_notifications | StatsPercentValue | Percentage of subscribers with enabled notifications |
| growth_graph | StatsGraph | Channel growth graph (absolute subscriber count) |
| followers_graph | StatsGraph | Followers growth graph (relative subscriber count) |
| mute_graph | StatsGraph | Muted users graph (relative) |
| top_hours_graph | StatsGraph | Views per hour graph (absolute) |
| interactions_graph | StatsGraph | Interactions graph (absolute) |
| iv_interactions_graph | StatsGraph | IV interactions graph (absolute) |
| views_by_source_graph | StatsGraph | Views by source graph (absolute) |
| new_followers_by_source_graph | StatsGraph | New followers by source graph (absolute) |
| languages_graph | StatsGraph | Subscriber language graph (pie chart) |
| reactions_by_emotion_graph | StatsGraph | A graph containing the number of reactions on posts categorized by emotion |
| story_interactions_graph | StatsGraph | A graph containing the number of story views and shares |
| story_reactions_by_emotion_graph | StatsGraph | A graph containing the number of reactions on stories categorized by emotion |
| recent_posts_interactions | Vector<PostInteractionCounters> | Detailed statistics about number of views and shares of recently sent messages and stories |


## Type
stats.BroadcastStats

## Related pages
