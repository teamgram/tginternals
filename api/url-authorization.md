# Seamless Telegram Login
Bots or Telegram websites may ask users to login to a certain website via Telegram when clicking on certain links or URL buttons in inline keyboards.
### Bot URL authorization
When the user clicks on keyboardButtonUrlAuth, messages.requestUrlAuth should be called, providing the button_id of the button and the ID and peer of the container message.
The returned urlAuthResultRequest object will contain more details about the authorization request:
- The domain parameter will contain the domain name of the website on which the user will log in (example: comments.app).
- The bot parameter will contain info about the bot which will be used for user authorization (example: DiscussBot).
- The request_write_access will be set if the bot would like to send messages to the user.
The info should be shown in a prompt:
If the user agrees to login to the URL, messages.acceptUrlAuth should be called (eventually setting the write_allowed if the permission was requested and the user consented).
The result will be a urlAuthResultAccepted with the final URL to open, which will include a query string with the requested info and a hash that must be verified upon receival by the service.
urlAuthResultDefault could also be returned, instead, in which case the url of the keyboardButtonUrlAuth must be opened, instead.
The same must be done if the user opens the link while refusing the authorization request.
### Link URL authorization
Telegram supports automatic authorization on certain websites upon opening an HTTP URL in-app, upon clicking a link in a message or clicking on a keyboardButtonUrl.
#### Automatic authorization
Clients should automatically authenticate users when opening official Telegram websites, listed in the autologin_domains key of the client configuration object ».
Upon clicking a link, the URL must be modified by appending the autologin_token » from the MTProto configuration object » to the query string, like so:
Original URL: https://somedomain.telegram.org/path?query=string#fragment=value
Modified URL: https://somedomain.telegram.org/path?query=string&autologin_token=$autologin_token#fragment=value
Make sure that the used autologin_token is no more than 10000 seconds old, if it is older it must be refetched before use with help.getConfig.
#### Manual authorization
Clients should show a confirmation prompt similar to the one used for bots, to authenticate users when opening certain Telegram websites, listed in the url_auth_domains key of the client configuration object ».
messages.requestUrlAuth should be called, providing only the original url.
The returned urlAuthResultRequest object will contain more details about the authorization request:
- The domain parameter will contain the domain name of the website on which the user will log in (example: comments.app).
- The request_write_access will be set if the website would like to send messages to the user.
The info should be shown in a prompt.
If the user agrees to login to the URL, messages.acceptUrlAuth should be called (eventually setting the write_allowed if the permission was requested and the user consented).
The result will be a urlAuthResultAccepted with the final URL to open.
urlAuthResultDefault could also be returned, instead, in which case the original URL must be opened, instead.
The same must be done if the user opens the link while refusing the authorization request.
### Related articles
#### Client configuration
The MTProto API has multiple configuration parameters that can be fetched with the appropriate methods.
