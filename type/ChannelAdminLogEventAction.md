# ChannelAdminLogEventAction
Channel admin log event

```
channelAdminLogEventActionChangeTitle#e6dfb825 prev_value:string new_value:string = ChannelAdminLogEventAction;
channelAdminLogEventActionChangeAbout#55188a2e prev_value:string new_value:string = ChannelAdminLogEventAction;
channelAdminLogEventActionChangeUsername#6a4afc38 prev_value:string new_value:string = ChannelAdminLogEventAction;
channelAdminLogEventActionChangePhoto#434bd2af prev_photo:Photo new_photo:Photo = ChannelAdminLogEventAction;
channelAdminLogEventActionToggleInvites#1b7907ae new_value:Bool = ChannelAdminLogEventAction;
channelAdminLogEventActionToggleSignatures#26ae0971 new_value:Bool = ChannelAdminLogEventAction;
channelAdminLogEventActionUpdatePinned#e9e82c18 message:Message = ChannelAdminLogEventAction;
channelAdminLogEventActionEditMessage#709b2405 prev_message:Message new_message:Message = ChannelAdminLogEventAction;
channelAdminLogEventActionDeleteMessage#42e047bb message:Message = ChannelAdminLogEventAction;
channelAdminLogEventActionParticipantJoin#183040d3 = ChannelAdminLogEventAction;
channelAdminLogEventActionParticipantLeave#f89777f2 = ChannelAdminLogEventAction;
channelAdminLogEventActionParticipantInvite#e31c34d8 participant:ChannelParticipant = ChannelAdminLogEventAction;
channelAdminLogEventActionParticipantToggleBan#e6d83d7e prev_participant:ChannelParticipant new_participant:ChannelParticipant = ChannelAdminLogEventAction;
channelAdminLogEventActionParticipantToggleAdmin#d5676710 prev_participant:ChannelParticipant new_participant:ChannelParticipant = ChannelAdminLogEventAction;
channelAdminLogEventActionChangeStickerSet#b1c3caa7 prev_stickerset:InputStickerSet new_stickerset:InputStickerSet = ChannelAdminLogEventAction;
channelAdminLogEventActionTogglePreHistoryHidden#5f5c95f1 new_value:Bool = ChannelAdminLogEventAction;
channelAdminLogEventActionDefaultBannedRights#2df5fc0a prev_banned_rights:ChatBannedRights new_banned_rights:ChatBannedRights = ChannelAdminLogEventAction;
channelAdminLogEventActionStopPoll#8f079643 message:Message = ChannelAdminLogEventAction;
channelAdminLogEventActionChangeLinkedChat#50c7ac8 prev_value:long new_value:long = ChannelAdminLogEventAction;
channelAdminLogEventActionChangeLocation#e6b76ae prev_value:ChannelLocation new_value:ChannelLocation = ChannelAdminLogEventAction;
channelAdminLogEventActionToggleSlowMode#53909779 prev_value:int new_value:int = ChannelAdminLogEventAction;
channelAdminLogEventActionStartGroupCall#23209745 call:InputGroupCall = ChannelAdminLogEventAction;
channelAdminLogEventActionDiscardGroupCall#db9f9140 call:InputGroupCall = ChannelAdminLogEventAction;
channelAdminLogEventActionParticipantMute#f92424d2 participant:GroupCallParticipant = ChannelAdminLogEventAction;
channelAdminLogEventActionParticipantUnmute#e64429c0 participant:GroupCallParticipant = ChannelAdminLogEventAction;
channelAdminLogEventActionToggleGroupCallSetting#56d6a247 join_muted:Bool = ChannelAdminLogEventAction;
channelAdminLogEventActionParticipantJoinByInvite#fe9fc158 flags:# via_chatlist:flags.0?true invite:ExportedChatInvite = ChannelAdminLogEventAction;
channelAdminLogEventActionExportedInviteDelete#5a50fca4 invite:ExportedChatInvite = ChannelAdminLogEventAction;
channelAdminLogEventActionExportedInviteRevoke#410a134e invite:ExportedChatInvite = ChannelAdminLogEventAction;
channelAdminLogEventActionExportedInviteEdit#e90ebb59 prev_invite:ExportedChatInvite new_invite:ExportedChatInvite = ChannelAdminLogEventAction;
channelAdminLogEventActionParticipantVolume#3e7f6847 participant:GroupCallParticipant = ChannelAdminLogEventAction;
channelAdminLogEventActionChangeHistoryTTL#6e941a38 prev_value:int new_value:int = ChannelAdminLogEventAction;
channelAdminLogEventActionParticipantJoinByRequest#afb6144a invite:ExportedChatInvite approved_by:long = ChannelAdminLogEventAction;
channelAdminLogEventActionToggleNoForwards#cb2ac766 new_value:Bool = ChannelAdminLogEventAction;
channelAdminLogEventActionSendMessage#278f2868 message:Message = ChannelAdminLogEventAction;
channelAdminLogEventActionChangeAvailableReactions#be4e0ef8 prev_value:ChatReactions new_value:ChatReactions = ChannelAdminLogEventAction;
channelAdminLogEventActionChangeUsernames#f04fb3a9 prev_value:Vector<string> new_value:Vector<string> = ChannelAdminLogEventAction;
channelAdminLogEventActionToggleForum#2cc6383 new_value:Bool = ChannelAdminLogEventAction;
channelAdminLogEventActionCreateTopic#58707d28 topic:ForumTopic = ChannelAdminLogEventAction;
channelAdminLogEventActionEditTopic#f06fe208 prev_topic:ForumTopic new_topic:ForumTopic = ChannelAdminLogEventAction;
channelAdminLogEventActionDeleteTopic#ae168909 topic:ForumTopic = ChannelAdminLogEventAction;
channelAdminLogEventActionPinTopic#5d8d353b flags:# prev_topic:flags.0?ForumTopic new_topic:flags.1?ForumTopic = ChannelAdminLogEventAction;
channelAdminLogEventActionToggleAntiSpam#64f36dfc new_value:Bool = ChannelAdminLogEventAction;
channelAdminLogEventActionChangePeerColor#5796e780 prev_value:PeerColor new_value:PeerColor = ChannelAdminLogEventAction;
channelAdminLogEventActionChangeProfilePeerColor#5e477b25 prev_value:PeerColor new_value:PeerColor = ChannelAdminLogEventAction;
channelAdminLogEventActionChangeWallpaper#31bb5d52 prev_value:WallPaper new_value:WallPaper = ChannelAdminLogEventAction;
channelAdminLogEventActionChangeEmojiStatus#3ea9feb1 prev_value:EmojiStatus new_value:EmojiStatus = ChannelAdminLogEventAction;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| channelAdminLogEventActionChangeTitle | Channel/supergroup title was changed |
| channelAdminLogEventActionChangeAbout | The description was changed |
| channelAdminLogEventActionChangeUsername | Channel/supergroup username was changed |
| channelAdminLogEventActionChangePhoto | The channel/supergroup's picture was changed |
| channelAdminLogEventActionToggleInvites | Invites were enabled/disabled |
| channelAdminLogEventActionToggleSignatures | Channel signatures were enabled/disabled |
| channelAdminLogEventActionUpdatePinned | A message was pinned |
| channelAdminLogEventActionEditMessage | A message was edited |
| channelAdminLogEventActionDeleteMessage | A message was deleted |
| channelAdminLogEventActionParticipantJoin | A user has joined the group (in the case of big groups, info of the user that has joined isn't shown) |
| channelAdminLogEventActionParticipantLeave | A user left the channel/supergroup (in the case of big groups, info of the user that has joined isn't shown) |
| channelAdminLogEventActionParticipantInvite | A user was invited to the group |
| channelAdminLogEventActionParticipantToggleBan | The banned rights of a user were changed |
| channelAdminLogEventActionParticipantToggleAdmin | The admin rights of a user were changed |
| channelAdminLogEventActionChangeStickerSet | The supergroup's stickerset was changed |
| channelAdminLogEventActionTogglePreHistoryHidden | The hidden prehistory setting was changed |
| channelAdminLogEventActionDefaultBannedRights | The default banned rights were modified |
| channelAdminLogEventActionStopPoll | A poll was stopped |
| channelAdminLogEventActionChangeLinkedChat | The linked chat was changed |
| channelAdminLogEventActionChangeLocation | The geogroup location was changed |
| channelAdminLogEventActionToggleSlowMode | Slow mode setting for supergroups was changed |
| channelAdminLogEventActionStartGroupCall | A group call was started |
| channelAdminLogEventActionDiscardGroupCall | A group call was terminated |
| channelAdminLogEventActionParticipantMute | A group call participant was muted |
| channelAdminLogEventActionParticipantUnmute | A group call participant was unmuted |
| channelAdminLogEventActionToggleGroupCallSetting | Group call settings were changed |
| channelAdminLogEventActionParticipantJoinByInvite | A user joined the supergroup/channel using a specific invite link |
| channelAdminLogEventActionExportedInviteDelete | A chat invite was deleted |
| channelAdminLogEventActionExportedInviteRevoke | A specific invite link was revoked |
| channelAdminLogEventActionExportedInviteEdit | A chat invite was edited |
| channelAdminLogEventActionParticipantVolume | channelAdminLogEvent.user_id has set the volume of participant.peer to participant.volume |
| channelAdminLogEventActionChangeHistoryTTL | The Time-To-Live of messages in this chat was changed |
| channelAdminLogEventActionParticipantJoinByRequest | A new member was accepted to the chat by an admin |
| channelAdminLogEventActionToggleNoForwards | Forwards were enabled or disabled |
| channelAdminLogEventActionSendMessage | A message was posted in a channel |
| channelAdminLogEventActionChangeAvailableReactions | The set of allowed message reactions » for this channel has changed |
| channelAdminLogEventActionChangeUsernames | The list of usernames associated with the channel was changed |
| channelAdminLogEventActionToggleForum | Forum functionality was enabled or disabled. |
| channelAdminLogEventActionCreateTopic | A forum topic was created |
| channelAdminLogEventActionEditTopic | A forum topic was edited |
| channelAdminLogEventActionDeleteTopic | A forum topic was deleted |
| channelAdminLogEventActionPinTopic | A forum topic was pinned or unpinned |
| channelAdminLogEventActionToggleAntiSpam | Native antispam functionality was enabled or disabled. |
| channelAdminLogEventActionChangePeerColor | The message accent color was changed |
| channelAdminLogEventActionChangeProfilePeerColor | The profile accent color was changed |
| channelAdminLogEventActionChangeWallpaper | The wallpaper was changed |
| channelAdminLogEventActionChangeEmojiStatus | The emoji status was changed |


## Methods
| Method | Description |
| ---- | ----------- |


