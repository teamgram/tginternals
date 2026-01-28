# Sharing Button

A Telegram Sharing Button is an easy way to let users forward content from your website or app to their friends, Channels or Saved Messages on Telegram.

When a user presses the button, Telegram asks them to choose a chat, group or channel where your link will be shared. You can also add some text that describes the link – the user will be able to edit it before sending the message.

> Check out posts on the Telegram Blog for working examples of sharing buttons.

### Adding Telegram sharing buttons to your website

#### Widget Constructor

Use this constructor to get embeddable code for your website.







#### Custom buttons

Feel free to create your own custom UI for the button. The only thing you need to make it work is to point the user to this URL on click:

```
https://t.me/share/url?url={url}&text={text}
```

where {url} is the URL the user will be sharing and {text} is an optional description that will be included with the link. Both values should be URL-encoded.

Here is a sample code for PHP:

```
/**
 * @param string $url Absolute URL to share, e.g. "https://example.com/path/to/article?with=params"
 * @param string $text Optional comment to share URL with, e.g. "Check out this article!"
 * @return string Button HTML markup, feel free to modify to your taste
 */
function telegramForwardButton($url, $text = '') {
  $share_url = 'https://t.me/share/url?url='.rawurlencode($url).'&text='.rawurlencode($text);
  return "<a href=\"{$share_url}\">Share</a>";
}
```

You are welcome to use the Telegram Logos in your custom button design.

#### Integrations and libraries

- Sharing buttons on WordPress.com blogs

- AddToAny share buttons

If you have a library, plugin or integration script for Telegram sharing buttons, please contact @BotSupport and we'll add you to this list.

