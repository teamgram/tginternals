# Poll

Telegram allows sending polls and quizzes, that can be voted on by thousands, if not millions of users in chats and channels.

### Sending a poll

```
pollAnswer#ff16e2ca text:TextWithEntities option:bytes = PollAnswer;

poll#58747131 id:long flags:# closed:flags.0?true public_voters:flags.1?true multiple_choice:flags.2?true quiz:flags.3?true question:TextWithEntities answers:Vector<PollAnswer> close_period:flags.4?int close_date:flags.5?int = Poll;

inputMediaPoll#f94e5f1 flags:# poll:Poll correct_answers:flags.0?Vector<bytes> solution:flags.1?string solution_entities:flags.1?Vector<MessageEntity> = InputMedia;

---functions---

messages.sendMedia#ac55d9c1 flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true allow_paid_floodskip:flags.19?true peer:InputPeer reply_to:flags.0?InputReplyTo media:InputMedia message:string random_id:long reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.10?int send_as:flags.13?InputPeer quick_reply_shortcut:flags.17?InputQuickReplyShortcut effect:flags.18?long allow_paid_stars:flags.21?long suggested_post:flags.22?SuggestedPost = Updates;
```

To send a poll in a chat, call messages.sendMedia, providing an inputMediaPoll:

- poll is the actual poll constructor, containing:

- question - The poll title, aka the poll's title

- answers - A vector of possible answers (2-poll_answers_max), each with a visible title text , and a unique option identifier (1-100 bytes)

- closed - Whether the poll is closed

- public_voters - Whether cast votes are publicly visible to all users (non-anonymous poll)

- multiple_choice - Whether multiple options can be chosen as answer

- quiz - Whether this is a quiz with correct answer IDs specified in inputMediaPoll.correct_answers

- close_period - Amount of time in seconds the poll will be active after creation, 5-600. Can't be used together with close_date .

- close_date - Point in time (Unix timestamp) when the poll will be automatically closed. Must be at least 5 and no more than 600 seconds in the future; can't be used together with close_period .

- These last two parameters are exactly the same, except that one uses absolute, the other relative unixtime.

- correct_answers - For quizzes, option ID of the only correct answer

- solution - Text that is shown when a user chooses an incorrect answer or taps on the lamp icon in a quiz-style poll, 0-200 characters with at most 2 line feeds

- solution_entities - Styled text message entities for the solution explanation

In order to prematurely close the poll, preventing further votes, use messages.editMessage, setting the poll.closed flag to true.

### Voting in polls

```
pollAnswerVoters#3b6ddad2 flags:# chosen:flags.0?true correct:flags.1?true option:bytes voters:int = PollAnswerVoters;

pollResults#7adf2420 flags:# min:flags.0?true results:flags.1?Vector<PollAnswerVoters> total_voters:flags.2?int recent_voters:flags.3?Vector<Peer> solution:flags.4?string solution_entities:flags.4?Vector<MessageEntity> = PollResults;

poll#58747131 id:long flags:# closed:flags.0?true public_voters:flags.1?true multiple_choice:flags.2?true quiz:flags.3?true question:TextWithEntities answers:Vector<PollAnswer> close_period:flags.4?int close_date:flags.5?int = Poll;

messageMediaPoll#4bd6e798 poll:Poll results:PollResults = MessageMedia;

updateMessagePoll#aca1657b flags:# poll_id:long poll:flags.0?Poll results:PollResults = Update;

---functions---

messages.sendVote#10ea6184 peer:InputPeer msg_id:int options:Vector<bytes> = Updates;
```

When receiving a message with a messageMediaPoll, users can vote in it using messages.sendVote, specifying the chosen option identifiers.

The method will return an updateMessagePoll, containing an updated pollResults constructor, with the chosen flag set on the options we chose, and the correct flag set on the correct answers.

### Getting poll votes

```
pollAnswerVoters#3b6ddad2 flags:# chosen:flags.0?true correct:flags.1?true option:bytes voters:int = PollAnswerVoters;

pollResults#7adf2420 flags:# min:flags.0?true results:flags.1?Vector<PollAnswerVoters> total_voters:flags.2?int recent_voters:flags.3?Vector<Peer> solution:flags.4?string solution_entities:flags.4?Vector<MessageEntity> = PollResults;

updateMessagePoll#aca1657b flags:# poll_id:long poll:flags.0?Poll results:PollResults = Update;

---functions---

messages.getPollResults#73bb643b peer:InputPeer msg_id:int = Updates;
```

Regularly, if new users have voted in polls available to the user, they will receive an updateMessagePoll, with updated pollResults.

The same constructor can also be fetched manually using messages.getPollResults.

### Getting poll voters in non-anonymous polls

```
messagePeerVote#b6cc2d5c peer:Peer option:bytes date:int = MessagePeerVote;
messagePeerVoteInputOption#74cda504 peer:Peer date:int = MessagePeerVote;
messagePeerVoteMultiple#4628f6e6 peer:Peer options:Vector<bytes> date:int = MessagePeerVote;

messages.votesList#4899484e flags:# count:int votes:Vector<MessagePeerVote> chats:Vector<Chat> users:Vector<User> next_offset:flags.0?string = messages.VotesList; 

updateMessagePollVote#24f40e77 poll_id:long peer:Peer options:Vector<bytes> qts:int = Update;

---functions---

messages.getPollVotes#b86e380e flags:# peer:InputPeer id:int option:flags.0?bytes offset:flags.1?string limit:int = messages.VotesList;
```

messages.getPollVotes can be used to get poll results for non-anonymous polls, to see how each user voted for a poll option.
Bots will also receive an updateMessagePollVote every time a user their answer in a non-anonymous poll. Bots receive new votes only in polls that were sent by the bot itself.

