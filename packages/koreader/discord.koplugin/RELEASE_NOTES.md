# v1.4.0 · 2026-11-23

v1.4.0

Roadmap v5: messaging, threads, navigation, reading, and moderation improvements. Japanese translation and TLS memory fix.


Changes since v1.3.0:
- Version 1.4.0
- Fix memory growth from TLS connections
- Merge pull request #81 from DEV-AdriBOT/add-japanese-translation
- Add Japanese translation
- Use channel membership for user thread follow state
- Fail closed when TLS verification has no CA bundle
- Downloads go to the device's documents folder by default; fix a nil start time in the reading activity
- Merge PR #79: QR code login, verified TLS connections, replies without pinging
- Spanish translations and README for the new features
- Moderation basics: delete, time out, kick and read the audit log
- Book club: optional summary of the reading session when closing the book
- Look up words from a message and send dictionary results to a chat
- Start threads from a message and follow or leave them
- Attachments: sizes in the chat, download with title, author and tags
- Send later: scheduled messages in the outbox
- Slash shortcuts, hidden spoilers and code blocks, mark unread from here, jump to a date or message
- Merge pull request #1 from rcdri/feature/qr-login-secure-connections
- README and translations for QR login, secure connections and replies
- Reply without pinging, no repaints under the keyboard, flag emoji
- Log in with a QR code
- Verify TLS certificates, add HTTP proxy support
- README: document the new features

# v1.3.0 · 2026-11-03

Offline send queue; emoji picker by name (writing and reacting, custom server emojis); hold a message to open its actions and tap a reply line to jump to the original; live edits and deletions with previous text; saved messages; multiple accounts; user profiles; member list with status; unread counter in the reader status bar; share the current page as an image; book club (progress and highlights); report a problem (QR); fixes.


Changes since v1.2.1:
- Version 1.3.0
- Fixes after testing on the device
- Share the current page and book club
- Report a problem
- Unread mentions and DMs counter in the reader status bar
- User profile and member list
- Multiple accounts
- Saved messages
- Live edits and deletions in the open chat
- Jump to the original message from a reply line
- Open message actions from the chat
- Emoji picker by name
- Offline send queue
- Release workflow: use the annotated tag message for the notes

# v1.2.1 · 2026-10-30

Works with KOReader's App Store: install and get update notices from Tools → App Store. The version now lives in _meta.lua, and releases are published automatically.

Changes since v1.2.0:
- Work with KOReader's App Store
- Translation progress table in the README

# v1.2.0 · 2026-10-30

- Choose the plugin language in Discord → Settings → Language (or keep following KOReader's language).
- Translations are now easy to contribute: see CONTRIBUTING.md. Regional variants such as pt_BR are supported.
- The update dialog shows release notes without Markdown symbols.

# v1.1.1 · 2026-10-29

Fixes the built-in updater, which could not check for or download releases in 1.1.0.

If you have 1.1.0, install this version by hand once (unzip `discord.koplugin.zip` into KOReader's `plugins` folder); from then on *Tools → Discord → Check for updates* works.
