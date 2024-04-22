# Telegram Login Widget

> The Telegram login widget is a simple way to authorize users on your website.Check out this post for a general overview of the widget.

### Setting up a bot

To use the login widget, you'll need a Telegram bot.

We strongly recommend that the profile picture of the bot you use for authorization corresponds with your website‘s logo, and that the bot’s name reflects that connection.

Users will see this message when they log into your website:

It is more likely that users will log in if your bot has a name and logo they expect to see.

### Linking your domain to the bot

Once you have chosen a bot, send the /setdomain command to @Botfather to link your website's domain to the bot. Then configure your widget below and embed the code on your website.

### Widget configuration





### Receiving authorization data

After a successful authorization, the widget can return data in two ways:

- by redirecting the user to the URL specified in the data-auth-url attribute with the following parameters: id, first_name, last_name, username, photo_url, auth_date and hash;

- by calling the callback function data-onauth with the JSON-object containing id, first_name, last_name, username, photo_url, auth_date and hash fields.

### Checking authorization

You can verify the authentication and the integrity of the data received by comparing the received hash parameter with the hexadecimal representation of the HMAC-SHA-256 signature of the data-check-string with the SHA256 hash of the bot's token used as a secret key.

Data-check-string is a concatenation of all received fields, sorted in alphabetical order, in the format key=<value> with a line feed character ('\n', 0x0A) used as separator – e.g., 'auth_date=<auth_date>\nfirst_name=<first_name>\nid=<id>\nusername=<username>'.

The full check might look like:

To prevent the use of outdated data, you can additionally check the auth_date field, which contains a Unix timestamp when the authentication was received.

### Sample implementation

You can find sample PHP code for checking authorization and receiving data about a logged in user on this page.

