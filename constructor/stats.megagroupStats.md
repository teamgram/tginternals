# stats.megagroupStats
Supergroup statistics

```
stats.megagroupStats#ef7ff916 period:StatsDateRangeDays members:StatsAbsValueAndPrev messages:StatsAbsValueAndPrev viewers:StatsAbsValueAndPrev posters:StatsAbsValueAndPrev growth_graph:StatsGraph members_graph:StatsGraph new_members_by_source_graph:StatsGraph languages_graph:StatsGraph messages_graph:StatsGraph actions_graph:StatsGraph top_hours_graph:StatsGraph weekdays_graph:StatsGraph top_posters:Vector<StatsGroupTopPoster> top_admins:Vector<StatsGroupTopAdmin> top_inviters:Vector<StatsGroupTopInviter> users:Vector<User> = stats.MegagroupStats;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| period | StatsDateRangeDays | Period in consideration |
| members | StatsAbsValueAndPrev | Member count change for period in consideration |
| messages | StatsAbsValueAndPrev | Message number change for period in consideration |
| viewers | StatsAbsValueAndPrev | Number of users that viewed messages, for range in consideration |
| posters | StatsAbsValueAndPrev | Number of users that posted messages, for range in consideration |
| growth_graph | StatsGraph | Supergroup growth graph (absolute subscriber count) |
| members_graph | StatsGraph | Members growth (relative subscriber count) |
| new_members_by_source_graph | StatsGraph | New members by source graph |
| languages_graph | StatsGraph | Subscriber language graph (pie chart) |
| messages_graph | StatsGraph | Message activity graph (stacked bar graph, message type) |
| actions_graph | StatsGraph | Group activity graph (deleted, modified messages, blocked users) |
| top_hours_graph | StatsGraph | Activity per hour graph (absolute) |
| weekdays_graph | StatsGraph | Activity per day of week graph (absolute) |
| top_posters | Vector<StatsGroupTopPoster> | Info about most active group members |
| top_admins | Vector<StatsGroupTopAdmin> | Info about most active group admins |
| top_inviters | Vector<StatsGroupTopInviter> | Info about most active group inviters |
| users | Vector<User> | Info about users mentioned in statistics |


## Type
stats.MegagroupStats

## Related pages
