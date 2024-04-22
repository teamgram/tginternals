# Bot attachment menu and side menu entries

Bots can install attachment menu and side menu entries, offering conveniently accessible, versatile mini apps.

Schema:

Bots that have the bot_attach_menu flag set offer an attachment or side menu entry that can be added to the in-app attachment menu or main view side menu.

Use messages.getAttachMenuBot to get info about the attachment/side menu entry of a given bot, see the attachMenuBot constructor page for more info ».

The currently installed attachment/side menu list can be fetched using messages.getAttachMenuBots.

Use messages.toggleBotInAttachMenu to enable or disable the attachment and/or side menu of a given bot (the entries that must be installed or uninstalled depend on the values of the attachMenuBot.show_in_attach_menu and attachMenuBot.show_in_side_menu flags).
Changes made using this method will trigger an updateAttachMenuBots update in other clients, which should trigger a messages.getAttachMenuBots call to fetch the full updated list of installed attachment/side menu entries.
The attachment/side menu list should also be refreshed if the user changes the app's language in the settings.

Once an attachment/side menu is enabled for a certain user, the user.attach_menu_enabled flag will be set for the bot, and the attachMenuBot.inactive flag will be unset.

Clicking on the attachment/side menu entry should open the related attachment menu mini app, see here » and here » for more info on the required steps.

Attachment menus can be installed and opened through attachment/side menu deep links and through mini app links.

In particular, when clicking on such a link, messages.getAttachMenuBot should be invoked to check if the bot has an associated attachment/side menu entry, and if yes:

- If the attachMenuBot.inactive flag:

- ...is set, the attachment/side menu entry is not installed.

- Thus, before launching the mini app when clicking on a attachment/side menu deep link, the client should show a prompt to the user, asking to add the mini app to the attachment/side menu.

- Note that if the attachMenuBot.side_menu_disclaimer_needed flag is set, an additional mandatory checkbox to accept the mini apps TOS and a disclaimer indicating that this Mini App is not affiliated to Telegram should be shown in the installation prompt.

- If the user accepts, invoke messages.toggleBotInAttachMenu with the write_allowed flag set and proceed to the next step, otherwise abort the process.

- ...is not set, and the attachMenuBot.side_menu_disclaimer_needed flag is still set, an additional mandatory checkbox to accept the mini apps TOS and a disclaimer indicating that this Mini App is not affiliated to Telegram should be shown.

- If the user accepts, proceed to the next step, otherwise abort the process.

- Open the Mini App:

- If the link is a direct mini app link, open the Mini App regardless of the currently open Telegram chat (in fact, the Mini App should opened even if the client itself is minimized), as specified here ».

- For attachment/side menu links, check that the attachment menu can be opened in the chosen chat type by checking the attachMenuBot.peer_types field.

- If the chosen chat is supported, open the attachment menu mini app » as specified here ».

- Otherwise:

- If the user has just installed the attachment menu @ step 1, notify the user that the attachment menu was installed successfully.

- Otherwise, notify the user that the attachment menu webapp can't be opened in the specified chat.

