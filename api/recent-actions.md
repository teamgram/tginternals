# Admin log

Both supergroups and channels offer a so-called admin log, a log of recent relevant supergroup and channel actions, like the modification of group/channel settings or information on behalf of an admin, user kicks and bans, and more.

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
channelAdminLogEventActionChangeEmojiStickerSet#46d840ab prev_stickerset:InputStickerSet new_stickerset:InputStickerSet = ChannelAdminLogEventAction;

channelAdminLogEvent#1fad68cd id:long date:int user_id:long action:ChannelAdminLogEventAction = ChannelAdminLogEvent;

channels.adminLogResults#ed8af74d events:Vector<ChannelAdminLogEvent> chats:Vector<Chat> users:Vector<User> = channels.AdminLogResults;

channelAdminLogEventsFilter#ea107ae4 flags:# join:flags.0?true leave:flags.1?true invite:flags.2?true ban:flags.3?true unban:flags.4?true kick:flags.5?true unkick:flags.6?true promote:flags.7?true demote:flags.8?true info:flags.9?true settings:flags.10?true pinned:flags.11?true edit:flags.12?true delete:flags.13?true group_call:flags.14?true invites:flags.15?true send:flags.16?true forums:flags.17?true sub_extend:flags.18?true = ChannelAdminLogEventsFilter;

---functions---

channels.getAdminLog#33ddf480 flags:# channel:InputChannel q:string events_filter:flags.0?ChannelAdminLogEventsFilter admins:flags.1?Vector<InputUser> max_id:long min_id:long limit:int = channels.AdminLogResults;
```

channels.getAdminLog can be used to list recent admin activity.
A channelAdminLogEventsFilter can be used to filter out actions of a certain type, and the admins field can be used to show only actions by certain admins.
q can also be used to filter only logs matching a query string.

