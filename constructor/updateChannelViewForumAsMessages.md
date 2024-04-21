# updateChannelViewForumAsMessages
Users may also choose to display messages from all topics as if they were sent to a normal group, using a "View as messages" setting in the local client.
This setting only affects the current account, and is synced to other logged in sessions using the channels.toggleViewForumAsMessages method; invoking this method will update the value of the view_forum_as_messages flag of channelFull or dialog and emit an updateChannelViewForumAsMessages.

```
updateChannelViewForumAsMessages#7b68920 channel_id:long enabled:Bool = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel_id | long | The forum ID |
| enabled | Bool | The new value of the toggle. |


## Type
Update

## Related pages
