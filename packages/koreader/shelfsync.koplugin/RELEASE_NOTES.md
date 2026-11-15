# 1.8.4 · 2026-11-15

- (fix) Don't send a jump, e.g. following a link, a table of contents entry or Go to page, as reading progress. Going back afterwards sent nothing, so the jump stayed as your progress. Jumps are recognised by the location KOReader saves to its history before them. Pages read from there are still sent as usual, and closing the book with no page turned since a jump uses the page it started from.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#184)

# 1.8.3 · 2026-11-11

- (fix) Stop retrying a book's status lookup when the reader sleeps, Wi-Fi drops (with "Enable wifi on demand" off) or the provider is turned off. The retries kept going, so sleeping and waking while the lookup failed added more each time, and a provider that had been turned off could still look the book up and mark it as Currently Reading.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#183)

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
