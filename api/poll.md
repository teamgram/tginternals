# Poll

Telegram allows sending polls and quizzes, that can be voted on by thousands, if not millions of users in chats and channels.

### Sending a poll

To send a poll in a chat, call messages.sendMedia, providing an inputMediaPoll:

- poll is the actual poll constructor, containing:

- question - The poll title, aka the poll's title

- answers - A vector of possible answers (2-10), each with a visible title text , and a unique option identifier (1-100 bytes)

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

When receiving a message with a messageMediaPoll, users can vote in it using messages.sendVote, specifying the chosen option identifiers.

The method will return an updateMessagePoll, containing an updated pollResults constructor, with the chosen flag set on the options we chose, and the correct flag set on the correct answers.

### Getting poll votes

Regularly, if new users have voted in polls available to the user, they will receive an updateMessagePoll, with updated pollResults.

The same constructor can also be fetched manually using messages.getPollResults.

### Getting poll voters in non-anonymous polls

messages.getPollVotes can be used to get poll results for non-anonymous polls, to see how each user voted for a poll option.
Bots will also receive an updateMessagePollVote every time a user their answer in a non-anonymous poll. Bots receive new votes only in polls that were sent by the bot itself.

