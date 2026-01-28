# messageMediaGiveawayResults
A giveaway with public winners has finished, this constructor contains info about the winners.

```
messageMediaGiveawayResults#ceaa3ea1 flags:# only_new_subscribers:flags.0?true refunded:flags.2?true channel_id:long additional_peers_count:flags.3?int launch_msg_id:int winners_count:int unclaimed_count:int winners:Vector<long> months:flags.4?int stars:flags.5?long prize_description:flags.1?string until_date:int = MessageMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| only_new_subscribers | flags.0?true | If set, only new subscribers starting from the giveaway creation date participated in the giveaway. |
| refunded | flags.2?true | If set, the giveaway was canceled and was fully refunded. |
| channel_id | long | ID of the channel/supergroup that was automatically boosted by the winners of the giveaway for duration of the Premium subscription. |
| additional_peers_count | flags.3?int | Number of other channels that participated in the giveaway. |
| launch_msg_id | int | Identifier of the message with the giveaway in channel_id. |
| winners_count | int | Total number of winners in the giveaway. |
| unclaimed_count | int | Number of not-yet-claimed prizes. |
| winners | Vector<long> | Up to 100 user identifiers of the winners of the giveaway. |
| months | flags.4?int | Duration in months of each Telegram Premium subscription in the giveaway. |
| stars | flags.5?long | For Telegram Star giveaways, the total number of Telegram Stars being given away. |
| prize_description | flags.1?string | Can contain a textual description of additional giveaway prizes. |
| until_date | int | Point in time (Unix timestamp) when the winners were selected. May be bigger than winners selection date specified in initial parameters of the giveaway. |


## Type
MessageMedia

## Related pages
