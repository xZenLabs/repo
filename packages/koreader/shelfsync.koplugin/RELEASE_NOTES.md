# 1.8.2 · 2026-11-03

- (feat) Choose file types (e.g. cbz for manga) that are never linked automatically, under Settings > Auto Book Link.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#182)

# 1.8.1 · 2026-10-18

- (feat) Send Goodreads ratings in quarter stars, now that Goodreads takes them, instead of rounding down to whole stars.
- (feat) LibraryThing: when "Link book" finds no work (e.g. a new translation no member has added yet), search a book source such as the Vlaamse Centrale Catalogus or Amazon, and add the picked edition to create it.
- (fix) Don't ask to mark a book that's Read on LibraryThing as reading again when it's opened at its end; LibraryThing has no reading progress to sync.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#181)

# 1.8.0 · 2026-10-17

- (feat) 🌟 Add LibraryThing sync: sign in with a username and password or browser session cookies (which the cookie helper can fetch with `--service librarything`), link books (adding one to your library if needed), sync Currently reading / To read / Read through LibraryThing's collections and reading dates, set the finished date (a re-read gets reading dates of its own, keeping the earlier ones), choose which collection read books go to (Your library by default), and save ratings and reviews. LibraryThing has no reading progress, so none is sent. 🌟
- (fix) Say why "Link book" couldn't search (e.g. no network), instead of doing nothing (all providers).


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#180)

# 1.7.0 · 2026-10-07

- (feat) 🌟 Keep progress and finished status from KOReader that can't be sent (e.g. with Wi-Fi off) for up to 4 weeks, and send them once the network is back, even after the book is closed or from the file browser. On Goodreads and Fable, progress is only sent within a day. 🌟
- (fix) Run ShelfSync's handling when a book is closed, which never ran. Closing a book now sends or queues progress that hadn't been sent yet.
- (fix) Send each provider's updates one at a time, so a late response can't undo a newer status or progress change.
- (fix) Say when a status change or removal from the status menu fails, instead of failing silently.
- (fix) Show the review result when a provider rejects a review without giving a reason, instead of stopping without a message.
- (fix) Keep Goodreads finished dates accurate while preserving existing reviews and retrying date saves that fail.
- (fix) Wait for the Goodreads browser cookie refresher to return before retrying requests after WAF challenges.
- (fix) Let interrupted Goodreads requests retry after the reader handles the touch that interrupted them.
- (fix) Don't show a progress mismatch warning just after ShelfSync marks a book as Read.
- (fix) Linking a book no longer tries to mark it as Currently Reading after a failed status lookup (all providers).
- (fix) Opening a linked Goodreads book no longer does so when its shelf can't be read or is one ShelfSync doesn't track.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#170)

# 1.6.1 · 2026-10-06

- (feat) Add a Goodreads account connection check that verifies the cookie and uses the configured cookie refresher when the cookie is missing or expired.
- (fix) Allow Goodreads syncing when only Cookie Auto-Refresh URL is configured, and refresh rejected cookies after HTTP 403 responses.
- (fix) Goodreads shelf changes now send the cookies that came with their CSRF token. Without them, they could get a 404 "Page not found" page.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#161)
