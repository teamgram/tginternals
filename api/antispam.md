# Native antispam system
Admins of supergroups with a certain number of members can choose to unleash the full proactive power of Telegram's own antispam algorithms – turning on the new Aggressive mode for the automated spam filters.
Schema:
Native antispam functionality can be enabled for supergroups using channels.toggleAntiSpam, if the supergroup has at least telegram_antispam_group_size_min members, as specified by the client configuration parameters.
Once enabled, Telegram's native antispam system will start monitoring the supergrup, automatically deleting spam messages using the official Telegram Antispam bot, with ID equal to telegram_antispam_user_id, as specified by the client configuration parameters.
Note that this bot does not have to be added as participant or admin to the supergroup for the native antispam system to work, just invoking channels.toggleAntiSpam is enough; however, it should still be locally shown as a group admin when displaying the admin list to the user (clients should simply append it to the admin list without invoking channels.editAdmin).
False positive message deletions can be reported by admins by navigating through the admin log, and invoking channels.reportAntiSpamFalsePositive for mistaken channelAdminLogEventActionDeleteMessage events made by the telegram_antispam_user_id bot.
