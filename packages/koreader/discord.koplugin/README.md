# discord.koplugin

A lightweight Discord client for [KOReader](https://github.com/koreader/koreader), designed for e-ink devices (tested on a Kindle Paperwhite 11).

## Features

**Navigation**
- Servers with text, announcement and forum channels grouped by category; channels you can't see are hidden, read-only ones are marked
- Threads under their channel, forum posts, and archived threads
- Direct messages and group DMs, sorted by latest activity
- **Unread markers** (bold + `●`) and **mention counts** (`@3`) for servers, channels and DMs, respecting muted servers and channels
- **Favorites**: long-press a channel or DM to pin it to the top of the home screen
- **Hide servers** you don't use (long-press a server)
- **Search** in any list (DMs also match usernames)
- **Server folders** from your account, in the same order as the official client
- **Mark as read** a whole server or all DMs, and **mute / unmute** servers and channels
- **Mentions inbox** with every recent message that mentions you, opened in context
- **Friends** list and incoming friend requests (accept / ignore)
- **Status**: online, idle, do not disturb or invisible
- **Multiple accounts**: log in with several accounts and switch between them from *Accounts*; each keeps its own cache, offline chats, favorites, recents, saved messages and drafts
- **Saved messages**: save a message to read later; the list is in the Discord menu and the home screen, and works offline
- **User profiles** (name, bio, roles, servers in common) from a message's actions or by holding a friend, and a **member list** with online / idle / do not disturb / offline status

**Chat**
- **Real-time updates** through the Discord gateway (WebSocket), with polling as a fallback
- Day separators, grouped messages, replies, mentions, forwarded messages, embeds, polls and stickers as text
- **Server nicknames**
- **Typing indicator** ("X is typing…") and your own typing is sent while you write
- **Send, reply, edit, delete**, copy, and open a DM with any author
- **Reply without pinging**: an *@ on / @ off* switch when replying, like Discord's (remembered, also for queued messages)
- **Offline send queue**: if there is no network, messages wait as *pending* (cancellable) and are sent automatically when the connection returns
- **Emoji by name**: search `:fire:`-style emojis, including each server's custom emojis, when writing and reacting; `:name:` typed by hand is converted when sending
- **Hold a message** to open its actions directly (an option makes a tap do it too); **tap a reply line** to jump to the original message
- **Live edits and deletions**: a deleted message stays as *(deleted message)* (its text can still be read) and the previous text of an edited one can be viewed
- **Reactions**: shown under each message, add or remove them
- **Quick replies** (configurable) and a **mention picker** with member search
- **Pinned messages** and **search** within a channel, with "jump to message"
- **"New" separator** at the last read position when a channel has unread messages
- **Polls** with live results, and voting
- **Send later**: schedule a message for a time (in 15 minutes, tomorrow at 08:00, or any HH:MM); it is sent even if the chat is closed
- **Slash shortcuts** at the start of a message: `/shrug`, `/tableflip`, `/unflip`, `/lenny`, `/me`, `/spoiler`, `/bold`
- **Spoilers** stay hidden until you reveal them in the message actions; **code blocks** are shown as an indented block and open in a monospaced viewer
- **Mark unread from here**: hold a message to bring the channel back as unread from that point
- **Jump to a date or message**: a date (`2026-11-05`, `05/11/2026`), `yesterday`, `3d`, a message id or a message link
- **Threads**: start one from a message, and follow or leave it
- **Files**: attachments show their size and type; download them to a folder of your choice with the right extension and KOReader metadata (title, the sender as author, tags and where they came from), and open readable ones straight away
- **Moderation** (only what your account is allowed to do): delete other people's messages, time out or kick a member, and read the audit log
- **Drafts** kept per channel, even across restarts
- **Only messages for me**: a per-channel mode for busy channels
- **Forward** messages, and keep **private notes** on users
- **Images on demand**: download a screen-sized version and open it in KOReader's image viewer — never loaded automatically
- **Reading theme**: any font (including the Kindle's own), line spacing, margins and text size; **compact layout**
- **Page turning** like a book: swipe left/right or use page-turn keys, with a periodic full refresh for e-ink
- **No flashing while you type**: new messages and typing indicators don't repaint the chat under the keyboard; it refreshes once when you close it

**E-reader**
- **Notifications** for DMs and mentions while you read (optional background connection)
- **Open as document**: read a long channel as a paginated book in KOReader's reader
- **Send highlights** from a book to a chat (highlight menu → *Send to Discord*)
- **Dictionary and Wikipedia**: look up any word of a message, and send a result to a chat (*Send to Discord* in the dictionary popup)
- **Offline chats**: the latest messages of recent chats are saved and readable without Wi-Fi
- **Links as QR codes**, to open them on your phone
- **Sleep screen summary** (optional): unread DMs and mentions shown on the sleep screen
- **Share the current page** of the book you are reading, as a grayscale image, in a chat
- **Book club** (per book, optional): send your reading progress (every X % or per chapter), your highlights and, optionally, a summary of each reading session (time, pages, progress) to a channel
- **Status bar counter** (optional): unread mentions and DMs in KOReader's status bar while you read
- **Report a problem**: prepares a report (versions, device, recent Discord log lines, no token or private data) as a QR code with a pre-filled GitHub issue, and saves a copy to `discord-report.txt`
- **Reading activity** (optional): your profile shows "Playing KOReader" with the book title, author and progress while a book is open
- **Battery saver**: pauses the background connection and slows polling below a battery level
- **Fast start**: the connection state is cached on disk, lists open at once and sessions are resumed after restarts
- Common emoji rendered as text, since e-reader fonts lack emoji glyphs (country flags as `:flag_pt:`)
- **Secure connections**: server certificates and host names are verified on every connection (REST, real time and updates), so nobody on the same Wi-Fi can read your login or fake an update; optional **HTTP proxy** (*Settings → Network*)
- Interface in English, Spanish and Japanese (follows KOReader's language)

## Installation

### From KOReader's App Store

If you use the [App Store plugin](https://github.com/omer-faruq/appstore.koplugin): *Tools → App Store → Plugins*, search for **discord** and install. It also shows when a new version is available.

### By hand

1. Download `discord.koplugin.zip` from the [latest release](https://github.com/DEV-AdriBOT/discord.koplugin/releases/latest) and unzip it.
2. Copy the `discord.koplugin` folder into KOReader's `plugins` directory:
   - Kindle: `/mnt/us/koreader/plugins/`
   - Kobo: `/mnt/onboard/.adds/koreader/plugins/`
   - Other devices: the `plugins` folder inside your KOReader install
3. Restart KOReader.
4. Open **Tools → Discord**.

## Updating

Either from the App Store, or with the plugin's own *Tools → Discord → Check for updates*, which compares your version with the latest release, shows what changed and installs it. The plugin also checks once a day when you open Discord and lets you know (this can be turned off in Settings).

## Logging in

- **QR code** — the easiest option, nothing to type: open the Discord app on your phone, go to *Settings → Scan QR Code*, scan the code shown on the e-reader and approve.
- **Email and password** — the simplest option. If Discord asks for a captcha (common on new devices/IPs), use a token instead.
- **Token** — type or paste your user token.
- **Token file** — put your token in `/mnt/us/discord_token.txt` (Kindle) and choose *Load token from…*. The file is deleted once the login succeeds.

The token is stored in KOReader's settings folder (`settings/discord.lua`). Anyone with access to the device files can read it, so log out if you lend your device.

## Gestures

These actions are available in KOReader's gesture manager:

- *Open Discord*
- *Discord: direct messages*
- *Discord: open last chat*

## Translations

The interface follows KOReader's language, or the one chosen in *Discord → Settings → Language*.

<!-- translations:start -->
| Language | Code | Translated | Progress |
| --- | --- | --- | --- |
| English (source) | `en` | 515 / 515 | ![100 %](https://img.shields.io/badge/100%25-brightgreen) |
| Español | `es` | 515 / 515 | ![100 %](https://img.shields.io/badge/100%25-brightgreen) |
| 日本語 | `ja` | 515 / 515 | ![100 %](https://img.shields.io/badge/100%25-brightgreen) |
<!-- translations:end -->

All translations are done by hand. I'm a native speaker of English and Spanish, and I'm learning Japanese. If you spot a translation mistake, especially in Japanese, please open a [translation issue](../../issues/new?template=translation.yml).

Want the plugin in your language? No programming needed: see [CONTRIBUTING.md](CONTRIBUTING.md#translating-the-plugin), or open a [translation issue](../../issues/new?template=translation.yml).

## Contributing

Bug reports, ideas and pull requests are welcome; see [CONTRIBUTING.md](CONTRIBUTING.md).

**Contribution note:** The contributions by [@rcdri in PR #79](https://github.com/DEV-AdriBOT/discord.koplugin/pull/79) and the [v5 roadmap PR #3 in their fork](https://github.com/rcdri/discord.koplugin/pull/3) were generated with Claude Code. This disclosure applies to those contributions only, not to the rest of this codebase.

## Disclaimer

This is an unofficial client that uses your user account through Discord's API and gateway. Using third-party clients is against Discord's Terms of Service and could, in theory, lead to your account being flagged. Use it at your own risk.

## License

[AGPL-3.0](LICENSE).
