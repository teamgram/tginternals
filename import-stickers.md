# Importing Stickers to Telegram

The easiest way to create stickers on Telegram is to simply upload them using the @stickers bot. This bot can help you upload new stickers, create sticker packs and get usage stats for your stickers and packs.

Telegram also offers a platform for developers of apps that help users make their own stickers. For example, apps that allow people to upload pictures of themselves and turn them into stickers.

### Who is this for?

USE this:

- To help people make their own unique custom stickers.

- To help people migrate their unique custom stickers they created from another platform.

DON'T use this:

- To share stickers you uploaded with other Telegram users.

- Instead, just upload your stickers using the @stickers bot and share the link of your pack (e.g. https://t.me/addstickers/UtyaDuck).

In short, if a set of stickers is already available on Telegram – there's no need to import it!

### Sticker Importing Apps

As of version 7.8, Telegram apps support a simple API for importing stickers.

> WARNING: Each time a user imports stickers, a new sticker pack is created on Telegram. Do not use the importing feature to share stickers you made with other users. If you want to share your stickers, simply upload them using @stickers and share the link of your pack. For example, here's a link to install some Duck Stickers.

### Importing SDKs

We have created libraries and sample apps for iOS and Android which you can use to implement importing stickers to Telegram from your app.

### Sticker Formats

Telegram apps support two sticker types. Regardless of the type, each sticker must be associated with at least one emoji that expresses the emotion corresponding to the sticker.

#### Animated Stickers

Must be in TGS format, created using the Bodymovin-TG plugin for Adobe After Effects.

> Note: Animated .WEBP is NOT currently supported, only static .WEBP is supported for static stickers. Animated stickers must be in .TGS format. You can also import .WEBM video stickers.

Max. size: 64 KBDimensions: 512x512 pxFPS: 30-60 FPSMax. duration: 3 seconds

> For full technical details on Telegram animated stickers, see this page.

#### Video Stickers

Must be in WEBM format with VP9 and alpha channel encoding (transparency is a temporary requirement).

Max. size: 256 KBMax. dimensions: 512x512 px, at least one side of the image must be 512px.FPS: 30Max. duration: 3 seconds

#### Static Stickers

Must be in PNG or WEBP format with a transparent layer. All static stickers should use white stroke and shadow, exactly like in this example: StickerExample.psd

Max. size: 512 KBMax. dimensions: 512x512 px, at least one side of the image must be 512px.

