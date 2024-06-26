# Stories

Telegram users and channels can easily post and view stories through the API.

### Posting stories

Schema:

```
inputPeerSelf#7da07ec9 = InputPeer;
inputPeerChannel#27bcbbfc channel_id:long access_hash:long = InputPeer;

boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;

updateStory#75b3b798 peer:Peer story:StoryItem = Update;

updateStoryID#1bf335b9 id:int random_id:long = Update;

---functions---

stories.canSendStory#c7dfdfdd peer:InputPeer = Bool;
stories.sendStory#e4e6694b flags:# pinned:flags.2?true noforwards:flags.4?true fwd_modified:flags.7?true peer:InputPeer media:InputMedia media_areas:flags.5?Vector<MediaArea> caption:flags.0?string entities:flags.1?Vector<MessageEntity> privacy_rules:Vector<InputPrivacyRule> random_id:long period:flags.3?int fwd_from_id:flags.6?InputPeer fwd_from_story:flags.6?int = Updates;
stories.editStory#b583ba46 flags:# peer:InputPeer id:int media:flags.0?InputMedia media_areas:flags.3?Vector<MediaArea> caption:flags.1?string entities:flags.1?Vector<MessageEntity> privacy_rules:flags.2?Vector<InputPrivacyRule> = Updates;

stories.getChatsToSend#a56a8b60 = messages.Chats;
```

Before posting a story, clients should invoke stories.canSendStory, to make sure they can send stories to the specified peer (which can be inputPeerSelf to send the story as a normal user and inputPeerChannel to send a story as a channel).

Use stories.getChatsToSend to obtain a list of channels where the user can post stories; stories.canSendStory must still be used before uploading a story to make sure no other limit was reached, as described in the main documentation ».
Note that in order to obtain permission to post stories as a channel, it must be boosted, first, see here » for more info.

stories.canSendStory returns boolTrue only if:

- If we're trying to send a story as a channel:

- The current user is an administrator of the channel and has post_stories admin rights; otherwise, a CHAT_ADMIN_REQUIRED error is returned.

- AND the channel has received enough boosts to post the story »; otherwise, a BOOSTS_REQUIRED error is returned.

- If we're trying to send a story as the current user:

- The user can post stories according to the stories_posting client configuration parameter; otherwise, a PREMIUM_ACCOUNT_REQUIRED error is returned.

- AND The user hasn't hit the maximum active stories limit specified by the story_expiring_limit_* client configuration parameters; otherwise a STORIES_TOO_MUCH error is returned, indicating that the user should buy a Premium subscription, delete an active story, or wait for the oldest story to expire.

- AND The user hasn't hit the weekly story limit specified by the stories_sent_weekly_limit_* client configuration parameters; otherwise, a STORY_SEND_FLOOD_WEEKLY_%d error is returned, indicating the number of seconds to wait before posting a new story.

- AND The user hasn't hit the monthly story limit specified by the stories_sent_monthly_limit_* client configuration parameters; otherwise, a STORY_SEND_FLOOD_MONTHLY_%d error is returned, indicating the number of seconds to wait before posting a new story.

After checking if a story can be posted, the client may invoke stories.sendStory to upload the story.
Note that if any of the conditions changes in the period between the call to stories.canSendStory and stories.sendStory (for example, the user uploads a story from another client, reaching the weekly limit), the same errors listed above for stories.canSendStory will be emitted by stories.sendStory.

The parameters of stories.sendStory are fully described on the method page », here are some of the most important ones:

- peer: The peer to send the story as.

- media:  The story media.

- media_areas: Media areas associated to the story, see here » for more info.

- privacy_rules: A set of privacy rules » for the story as an array of InputPrivacyRule constructors, indicating who can or can't view the story.

- expire: Period after which the story is moved to archive (and to the profile if pinned is set), in seconds; must be one of 6 * 3600, 12 * 3600, 86400, or 2 * 86400 for Telegram Premium users, and 86400 otherwise.

- pinned: Whether to also add the story to the profile automatically upon expiration. If not set, the story will only be added to the archive.

- caption and entities: The story caption, and related styled text entities; note that the story caption length is limited by the story_caption_length_limit_* » config keys, and story entities should only be sent and displayed according to the value of the stories_entities » config key.

Once a story is successfully uploaded, an updateStoryID will be returned, indicating the story ID (id) that was attributed to the story (like for messages, random_id indicates the random_id that was passed to stories.sendStory: this way, you can tell which story was assigned a specific id by checking which stories.sendStory call has the returned random_id).

Also, posting a story will emit an updateStory both for us, and for our subscribers/contacts (even if they have hidden our stories).

Additionally, a message containing a messageMediaStory with the via_mention flag coming from the story poster will also be generated automatically if the poster mentions us in the story's caption.

A story may also be edited using stories.editStory.

#### Pinned or archived stories

```
stories.stories#5dd8c3c8 count:int stories:Vector<StoryItem> chats:Vector<Chat> users:Vector<User> = stories.Stories;

---functions---

stories.togglePinned#9a75a1ef peer:InputPeer id:Vector<int> pinned:Bool = Vector<int>;

stories.getStoriesArchive#b4352016 peer:InputPeer offset_id:int limit:int = stories.Stories;

stories.getPinnedStories#5821a5dc peer:InputPeer offset_id:int limit:int = stories.Stories;
```

After an active story expires, it is automatically added to the story archive: stories in the story archive are only visible to the poster.

Use stories.getStoriesArchive to fetch stories in the story archive.

Archived stories may then be pinned on the profile, where they may be fetched using stories.getPinnedStories by users who explicitly open your profile: use stories.togglePinned to pin or unpin one or more stories to your profile.

Stories may also be autopinned upon expiration if the pinned flag is set when posting them.

#### Deleting stories

```
---functions---

stories.deleteStories#ae59db5f peer:InputPeer id:Vector<int> = Vector<int>;
```

Use the stories.deleteStories method to delete one or more active, pinned or archived stories by their IDs, passed in id.

#### Preventing users from seeing your stories

Users may be individually blocked from seeing all of your stories by adding them to the story blocklist ».

### Watching stories

```
storyItem#af6365a1 flags:# pinned:flags.5?true public:flags.7?true close_friends:flags.8?true min:flags.9?true noforwards:flags.10?true edited:flags.11?true contacts:flags.12?true selected_contacts:flags.13?true out:flags.16?true id:int date:int fwd_from:flags.17?StoryFwdHeader expire_date:int caption:flags.0?string entities:flags.1?Vector<MessageEntity> media:MessageMedia media_areas:flags.14?Vector<MediaArea> privacy:flags.2?Vector<PrivacyRule> views:flags.3?StoryViews sent_reaction:flags.15?Reaction = StoryItem;
storyItemSkipped#ffadc913 flags:# close_friends:flags.8?true id:int date:int expire_date:int = StoryItem;
storyItemDeleted#51e6ee4f id:int = StoryItem;

peerStories#9a35e999 flags:# peer:Peer max_read_id:flags.0?int stories:Vector<StoryItem> = PeerStories;

storiesStealthMode#712e27fd flags:# active_until_date:flags.0?int cooldown_until_date:flags.1?int = StoriesStealthMode;

stories.allStories#6efc5e81 flags:# has_more:flags.0?true count:int state:string peer_stories:Vector<PeerStories> chats:Vector<Chat> users:Vector<User> stealth_mode:StoriesStealthMode = stories.AllStories;
stories.allStoriesNotModified#1158fe3e flags:# state:string stealth_mode:StoriesStealthMode = stories.AllStories;

stories.peerStories#cae68768 stories:PeerStories chats:Vector<Chat> users:Vector<User> = stories.PeerStories;

updateReadStories#f74e932b peer:Peer max_id:int = Update;

---functions---

stories.getAllStories#eeb0d625 flags:# next:flags.1?true hidden:flags.2?true state:flags.0?string = stories.AllStories;

stories.getStoriesByID#5774ca74 peer:InputPeer id:Vector<int> = stories.Stories;
stories.getPeerStories#2c4ada50 peer:InputPeer = stories.PeerStories;

stories.readStories#a556dac8 peer:InputPeer max_id:int = Vector<int>;
stories.incrementStoryViews#b2028afb peer:InputPeer id:Vector<int> = Bool;

stories.getAllReadPeerStories#9b5ae7f9 = Updates;
stories.getPeerMaxIDs#535983c3 id:Vector<InputPeer> = Vector<int>;
```

Active stories of contacts, subscribed channels and the changelog user should be shown in the action bar of the homescreen.
Use stories.getAllStories to fetch the full list of active stories.

Optionally, the hidden flag can be set to fetch the hidden stories to be shown in the archived tab, instead of the main story list.

Pagination using this method is a bit different from usual: a state string is used to maintain the pagination state.

- Initially, neither the next or state flags should be set: upon completion of the RPC call, a new state string is returned and should be stored locally, associated either to the main or hidden story list (depending on the value of hidden we passed); pass the locally stored state to all future calls of the method.

- If more stories are available, the returned stories.allStories.has_more flag will be set: in this case, the client should re-call the method with the newly returned state and the next flag set to fetch a new state and the remaining stories from the chosen story list; the process should be repeated until no more stories are available (has_more will not be set).

Once the full story list is fetched, stories.allStories can be called with the stored state without setting the next flag to check for updates in an active story list: if no changes have occurred since our last call, stories.allStoriesNotModified is returned, otherwise stories.allStories is returned (possibly requiring further pagination as described above).
Note that a change is currently only defined as an addition or removal (i.e. by moving it to the hidden list or vice versa) of a peer to/from a story list, not as a new story being posted; those changes are received as simple updateStory updates.

Changes to the active stories list are contained in the stories.allStories.peer_stories field: this field contains a vector of peerStories constructors, one for each peer, containing the peer ID, the ID of the maximum read story (if any), and a list of StoryItem constructors of type:

- storyItem - Represents an active story

- storyItemSkipped - Represents an active story, whose full information was omitted for space and performance reasons; use stories.getStoriesByID to fetch full info about the skipped story/stories when and if needed.

- storyItemDeleted - Represents a previously active story, that was now deleted

Use stories.getPeerStories may also be used to fetch the full active story list of a specific peer.

Use stories.readStories to mark all stories up to a certain ID as read, for a given peer: using this method will emit an updateReadStories update to all logged-in sessions if a newer ID is marked as read.
Use stories.getAllReadPeerStories to obtain the latest read story ID for all peers when first logging in, returned as a list of updateReadStories updates: further calls to this method are not needed after login, as updates to the latest read story ID will be sent using updateReadStories updates, with the usual update delivering methods.

Use stories.incrementStoryViews to actually increment the view counter of stories the user has seen (pass max 200 story IDs at a time).

#### Hiding stories of other users

```
user#215c4438 flags:# self:flags.10?true contact:flags.11?true mutual_contact:flags.12?true deleted:flags.13?true bot:flags.14?true bot_chat_history:flags.15?true bot_nochats:flags.16?true verified:flags.17?true restricted:flags.18?true min:flags.20?true bot_inline_geo:flags.21?true support:flags.23?true scam:flags.24?true apply_min_photo:flags.25?true fake:flags.26?true bot_attach_menu:flags.27?true premium:flags.28?true attach_menu_enabled:flags.29?true flags2:# bot_can_edit:flags2.1?true close_friend:flags2.2?true stories_hidden:flags2.3?true stories_unavailable:flags2.4?true id:long access_hash:flags.0?long first_name:flags.1?string last_name:flags.2?string username:flags.3?string phone:flags.4?string photo:flags.5?UserProfilePhoto status:flags.6?UserStatus bot_info_version:flags.14?int restriction_reason:flags.18?Vector<RestrictionReason> bot_inline_placeholder:flags.19?string lang_code:flags.22?string emoji_status:flags.30?EmojiStatus usernames:flags2.0?Vector<Username> stories_max_id:flags2.5?int color:flags2.8?PeerColor profile_color:flags2.9?PeerColor = User;

---functions---

stories.togglePeerStoriesHidden#bd0415c4 peer:InputPeer hidden:Bool = Bool;

stories.toggleAllStoriesHidden#7c2557c4 hidden:Bool = Bool;
```

Use stories.togglePeerStoriesHidden to hide the active stories of a specific peer, preventing them from being displayed on the action bar on the homescreen.
When the stories of a user are marked as hidden, the stories_hidden flag is set on the related user constructor, and they should only be visible on the action bar when opening the archive folder, by setting the hidden flag when calling stories.getAllStories, see here for more info.

Note that the archive folder is the peer folder used for archived chats: hidden stories are displayed there purely due to a UI implementation detail, not because they're actually added to the archive peer folder » or the story archive », which are different things.

### Sharing stories

```
inputMediaStory#89fdd778 peer:InputPeer id:int = InputMedia;

messageMediaStory#68cb6283 flags:# via_mention:flags.1?true peer:Peer id:int story:flags.0?StoryItem = MessageMedia;

---functions---

messages.sendMedia#72ccc23d flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true peer:InputPeer reply_to:flags.0?InputReplyTo media:InputMedia message:string random_id:long reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.10?int send_as:flags.13?InputPeer = Updates;
```

Stories can be shared as messages to any chat by simply using messages.sendMedia, passing an inputMediaStory referencing the shared story.

The story will be shared as a messageMediaStory, and should be displayed as a message forwarded from the poster of the story (even though messages.forwardMessages was not used an the fwd_from field of the message won't be set).

A message containing a messageMediaStory with the via_mention flag coming from the story poster will also be generated automatically if the poster mentions us in the story's caption.

### Fetching the interaction list

```
storyView#b0bdeac5 flags:# blocked:flags.0?true blocked_my_stories_from:flags.1?true user_id:long date:int reaction:flags.2?Reaction = StoryView;
storyViewPublicForward#9083670b flags:# blocked:flags.0?true blocked_my_stories_from:flags.1?true message:Message = StoryView;
storyViewPublicRepost#bd74cf49 flags:# blocked:flags.0?true blocked_my_stories_from:flags.1?true peer_id:Peer story:StoryItem = StoryView;

stories.storyViewsList#59d78fc5 flags:# count:int views_count:int forwards_count:int reactions_count:int views:Vector<StoryView> chats:Vector<Chat> users:Vector<User> next_offset:flags.0?string = stories.StoryViewsList;

storyReaction#6090d6d5 peer_id:Peer date:int reaction:Reaction = StoryReaction;
storyReactionPublicForward#bbab2643 message:Message = StoryReaction;
storyReactionPublicRepost#cfcd0f13 peer_id:Peer story:StoryItem = StoryReaction;

stories.storyReactionsList#aa5f789c flags:# count:int reactions:Vector<StoryReaction> chats:Vector<Chat> users:Vector<User> next_offset:flags.0?string = stories.StoryReactionsList;

storyViews#8d595cd6 flags:# has_viewers:flags.1?true views_count:int forwards_count:flags.2?int reactions:flags.3?Vector<ReactionCount> reactions_count:flags.4?int recent_viewers:flags.0?Vector<long> = StoryViews;
stories.storyViews#de9eed1d views:Vector<StoryViews> users:Vector<User> = stories.StoryViews;

---functions---

stories.getStoryViewsList#7ed23c57 flags:# just_contacts:flags.0?true reactions_first:flags.2?true forwards_first:flags.3?true peer:InputPeer q:flags.1?string id:int offset:string limit:int = stories.StoryViewsList;

stories.getStoryReactionsList#b9b2881f flags:# forwards_first:flags.2?true peer:InputPeer id:int reaction:flags.0?Reaction offset:flags.1?string limit:int = stories.StoryReactionsList;

stories.getStoriesViews#28e16cc8 peer:InputPeer id:Vector<int> = stories.StoryViews;
```

Use stories.getStoryViewsList to obtain the full list of users that have interacted with a specific story we posted as a user, returned as a list of StoryView constructors; pass the returned next_offset (if present) to offset to paginate through the results; the full list is available at all times only to Premium users, and will be deleted on stories posted by non-Premium users story_viewers_expire_period » seconds after the story expires; if it's still viewable, the has_viewers flag will be set.

The above method can only be used for stories posted by users, to fetch almost the exact same information for stories posted by channels, use stories.getStoryReactionsList: the data returned by both methods is actually almost exactly the same, the only difference is that:

- stories.getStoryViewsList can only be used for stories posted by the current user and also contains view and blocklist information.

- stories.getStoryReactionsList can only be used for stories posted by channels we're an admin of and does not contain view information

For the rest, both methods return information about:

- Story reactions: storyView/storyReaction

- Story forwards as a message to a public chat/channel: storyViewPublicForward/storyReactionPublicForward

- Story reposts (as a story to a public channel/user): storyViewPublicRepost/storyReactionPublicRepost

Additionally, stories.getStoriesViews can be used to obtain info about the view count, forward count, reactions and recent viewers list of one or more stories, using a single, unpaginated method call, obviously potentially returning less info than stories.getStoryViewsList.

### Replying to stories

```
inputReplyToStory#15b0f283 user_id:InputUser story_id:int = InputReplyTo;

---functions---

messages.sendMessage#280d096f flags:# no_webpage:flags.1?true silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true peer:InputPeer reply_to:flags.0?InputReplyTo message:string random_id:long reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.10?int send_as:flags.13?InputPeer = Updates;
```

You may reply to stories posted by users by using messages.sendMessage, messages.sendMedia or any other method used to send messages, passing an inputReplyToStory to reply_to, with the ID of the user that posted the story (which must also be the destination peer of the message) and the story ID.

### Reposting stories

```
storyFwdHeader#b826e150 flags:# modified:flags.3?true from:flags.0?Peer from_name:flags.1?string story_id:flags.2?int = StoryFwdHeader;

storyItem#af6365a1 flags:# pinned:flags.5?true public:flags.7?true close_friends:flags.8?true min:flags.9?true noforwards:flags.10?true edited:flags.11?true contacts:flags.12?true selected_contacts:flags.13?true out:flags.16?true id:int date:int fwd_from:flags.17?StoryFwdHeader expire_date:int caption:flags.0?string entities:flags.1?Vector<MessageEntity> media:MessageMedia media_areas:flags.14?Vector<MediaArea> privacy:flags.2?Vector<PrivacyRule> views:flags.3?StoryViews sent_reaction:flags.15?Reaction = StoryItem;

---functions---

stories.sendStory#e4e6694b flags:# pinned:flags.2?true noforwards:flags.4?true fwd_modified:flags.7?true peer:InputPeer media:InputMedia media_areas:flags.5?Vector<MediaArea> caption:flags.0?string entities:flags.1?Vector<MessageEntity> privacy_rules:Vector<InputPrivacyRule> random_id:long period:flags.3?int fwd_from_id:flags.6?InputPeer fwd_from_story:flags.6?int = Updates;
```

Stories may be reposted by using stories.sendStory, populating the fwd_from_story field with the original story ID and the fwd_from_id with the peer that posted the original story.

The user may modify the story (for example by overlaying a round video reaction on top of the media); either way, the modified or the original media must be passed to the media field as usual, and the fwd_modified flag must be set if the media was modified.

Reposted stories will have the storyItem set and populated with a storyFwdHeader constructor, containing info about the original story.

### Reporting stories

```
inputReportReasonSpam#58dbcab8 = ReportReason;
inputReportReasonViolence#1e22c78d = ReportReason;
inputReportReasonPornography#2e59d922 = ReportReason;
inputReportReasonChildAbuse#adf44ee3 = ReportReason;
inputReportReasonOther#c1e4a2b1 = ReportReason;
inputReportReasonCopyright#9b89f93a = ReportReason;
inputReportReasonGeoIrrelevant#dbd4feed = ReportReason;
inputReportReasonFake#f5ddd6e7 = ReportReason;
inputReportReasonIllegalDrugs#a8eb2be = ReportReason;
inputReportReasonPersonalDetails#9ec7863d = ReportReason;

---functions---

stories.report#1923fa8c peer:InputPeer id:Vector<int> reason:ReportReason message:string = Bool;
```

Use stories.report to report one or more stories.

### Story links

```
exportedStoryLink#3fc9053b link:string = ExportedStoryLink;

---functions---

stories.exportStoryLink#7b8def20 peer:InputPeer id:int = ExportedStoryLink;
```

Use stories.exportStoryLink to generate a story deep link for a specific story.

Upon encountering a story deep link, clients should open the specified story as specified here ».

See here » for more info on story deep links.

### Media areas

Schema:

```
mediaAreaCoordinates#3d1ea4e x:double y:double w:double h:double rotation:double = MediaAreaCoordinates;

mediaAreaVenue#be82db9c coordinates:MediaAreaCoordinates geo:GeoPoint title:string address:string provider:string venue_id:string venue_type:string = MediaArea;
inputMediaAreaVenue#b282217f coordinates:MediaAreaCoordinates query_id:long result_id:string = MediaArea;
mediaAreaGeoPoint#df8b3b22 coordinates:MediaAreaCoordinates geo:GeoPoint = MediaArea;
mediaAreaSuggestedReaction#14455871 flags:# dark:flags.0?true flipped:flags.1?true coordinates:MediaAreaCoordinates reaction:Reaction = MediaArea;

storyItem#af6365a1 flags:# pinned:flags.5?true public:flags.7?true close_friends:flags.8?true min:flags.9?true noforwards:flags.10?true edited:flags.11?true contacts:flags.12?true selected_contacts:flags.13?true out:flags.16?true id:int date:int fwd_from:flags.17?StoryFwdHeader expire_date:int caption:flags.0?string entities:flags.1?Vector<MessageEntity> media:MessageMedia media_areas:flags.14?Vector<MediaArea> privacy:flags.2?Vector<PrivacyRule> views:flags.3?StoryViews sent_reaction:flags.15?Reaction = StoryItem;

---functions---

stories.sendStory#e4e6694b flags:# pinned:flags.2?true noforwards:flags.4?true fwd_modified:flags.7?true peer:InputPeer media:InputMedia media_areas:flags.5?Vector<MediaArea> caption:flags.0?string entities:flags.1?Vector<MessageEntity> privacy_rules:Vector<InputPrivacyRule> random_id:long period:flags.3?int fwd_from_id:flags.6?InputPeer fwd_from_story:flags.6?int = Updates;
stories.editStory#b583ba46 flags:# peer:InputPeer id:int media:flags.0?InputMedia media_areas:flags.3?Vector<MediaArea> caption:flags.1?string entities:flags.1?Vector<MessageEntity> privacy_rules:flags.2?Vector<InputPrivacyRule> = Updates;
```

Stories can have so-called "media areas": clickable rectangular areas with animated overlays on top of the story offering functionality like location tags or reactions.

The coordinates and size of each media area is specified in a mediaAreaCoordinates constructor attached to each MediaArea, see the constructor page » for more info.

After construction, the vector of MediaArea constructors can be passed to stories.sendStory or stories.editStory.

#### Channel posts

```
inputMediaAreaChannelPost#2271f2bf coordinates:MediaAreaCoordinates channel:InputChannel msg_id:int = MediaArea;

mediaAreaChannelPost#770416af coordinates:MediaAreaCoordinates channel_id:long msg_id:int = MediaArea;
```

Messages from channels can be reposted to stories using inputMediaAreaChannelPost/mediaAreaChannelPost.

Clients should fetch and display a copy of the channel post on top of the story according to the media area coordinates: clicking on the media area should open the linked post.

#### Location tags

Schema:

```
geoPoint#b2a2f663 flags:# long:double lat:double access_hash:long accuracy_radius:flags.0?int = GeoPoint;

mediaAreaGeoPoint#df8b3b22 coordinates:MediaAreaCoordinates geo:GeoPoint = MediaArea;
mediaAreaVenue#be82db9c coordinates:MediaAreaCoordinates geo:GeoPoint title:string address:string provider:string venue_id:string venue_type:string = MediaArea;

inputMediaAreaVenue#b282217f coordinates:MediaAreaCoordinates query_id:long result_id:string = MediaArea;
```

Location tags are represented by a mediaAreaVenue or mediaAreaGeoPoint, associated to a location sticker on top of the story media with an associated clickable media area.

Both constructors have an associated geolocation represented as a geoPoint, and information about the clickable media area on top of the story media as a mediaAreaCoordinates constructor.

mediaAreaGeoPoint is used to represent a simple geolocation without any extra information.
mediaAreaVenue is used to represent the location of a specific venue (i.e. a mall, a shop, a dance school et cetera), and apart from the venue's coordinates, it also contains a textual representation of the address, the venue name (title) and a venue type/ID (venue_id/venue_type) in a format supported by the venue provider specified in provider.

Currently, the only provider that needs to be supported is foursquare.

To send a mediaAreaVenue, clients should use inputMediaAreaVenue, constructed as follows:

- If the user gives permission to share their location with the location provider, query the inline bot specified in the stories_venue_search_username client configuration parameter », as described as the inline queries documentation », populating the geo_point.

- Note that this should be done transparently in a map UI, not in the usual inline query UI in the chat text bar.

- The results returned by the bot, containing a list of venues close to the specified geo_point, should be listed in the lower section of the map UI: upon selection, construct the inputMediaAreaVenue with:

- query_id: the query_id from messages.botResults.

- result_id: the id of the chosen result.

Clients may only re-use existing mediaAreaVenues when repositioning a pre-existing location tag when editing a story; use inputMediaAreaVenue when posting a new story or adding a new location tag to an existing story.

#### Reactions

Schema:

```
reactionEmoji#1b2286b8 emoticon:string = Reaction;
reactionCustomEmoji#8935fc73 document_id:long = Reaction;

mediaAreaSuggestedReaction#14455871 flags:# dark:flags.0?true flipped:flags.1?true coordinates:MediaAreaCoordinates reaction:Reaction = MediaArea;

updateSentStoryReaction#7d627683 peer:Peer story_id:int reaction:Reaction = Update;

---functions---

stories.sendReaction#7fd736b2 flags:# add_to_recent:flags.0?true peer:InputPeer story_id:int reaction:Reaction = Updates;
```

Story reactions are implemented using a simple in-UI button that allows the user to send any reaction using stories.sendReaction.

Sending this method will return an updateSentStoryReaction update to all logged-in sessions.

However, the poster of a story may also use mediaAreaSuggestedReaction media areas » to suggest some specific reactions as simple clickable buttons: they're rendered as a round comic-style thought bubble with its "tail" on the right, white background and the reaction » from the reaction field located in its center.
If the dark flag is set, the background should be black.
If the flipped flag is set, the "tail" should be located on the left.
The maximum number of story reaction media areas that can be added to a story is specified by the stories_suggested_reactions_limit_* » config keys.
Clicking it should invoke stories.sendReaction as usual.

See here » to get more info on how to fetch the reaction list of a story.

### Stealth mode

Premium users may enable stealth mode, erasing their views from any stories they opened in the past stories_stealth_past_period seconds », and hiding their views on stories for the next stories_stealth_future_period seconds », as specified by the client configuration ».

Schema:

```
storiesStealthMode#712e27fd flags:# active_until_date:flags.0?int cooldown_until_date:flags.1?int = StoriesStealthMode;

updateStoriesStealthMode#2c084dc1 stealth_mode:StoriesStealthMode = Update;

---functions---

stories.activateStealthMode#57bbd166 flags:# past:flags.0?true future:flags.1?true = Updates;
```

Invoke stories.activateStealthMode to activate stealth mode, passing the past flag to erase views from any stories opened in the past stories_stealth_past_period seconds » and/or the future flag to hide future story views for the next stories_stealth_future_period seconds ».

Clients can only invoke this method every stories_stealth_cooldown_period seconds as specified by the client configuration: invoking the method before the cooldown period has expired will trigger a FLOOD_WAIT_X error, with X being the number of seconds left before the cooldown period expires.

An updateStoriesStealthMode constructor will be returned, containing the following fields:

- active_until_date - the date up to which stealth mode will be active

- cooldown_until_date - the date starting from which the user will be allowed to call stories.activateStealthMode again; calling the method earlier will return a FLOOD_WAIT_X error as specified above.

### Statistics

```
stats.storyStats#50cd067c views_graph:StatsGraph reactions_by_emotion_graph:StatsGraph = stats.StoryStats;

publicForwardMessage#1f2bf4a message:Message = PublicForward;
publicForwardStory#edf3add0 peer:Peer story:StoryItem = PublicForward;

stats.publicForwards#93037e20 flags:# count:int forwards:Vector<PublicForward> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = stats.PublicForwards;

---functions---

stats.getStoryStats#374fef40 flags:# dark:flags.0?true peer:InputPeer id:int = stats.StoryStats;

stats.getStoryPublicForwards#a6437ef6 peer:InputPeer id:int offset:string limit:int = stats.PublicForwards;
```

Use stats.getStoryStats to obtain statistics about a story; the returned StatsGraph graphs can be rendered as described here ».

Use stats.getStoryPublicForwards to obtain forwards of a story as a message to public chats and reposts by public channels.

