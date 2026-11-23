# 1.8.5 · 2026-11-23

- (feat) Add "Sync only when a reading session ends" to record one final progress update when a book is closed or the device sleeps, instead of at every time, percentage or page threshold. Progress is recorded without needing to reach a threshold, and no entry is added if the recorded position hasn't changed since the last sync.
- (fix) Keep the highlight "Add note" action available while a book's remote status is still loading, or when it is Read, Did Not Finish or To Read. It no longer greys out after reopening a book or connecting Wi-Fi until the status lookup succeeds.
- (fix) Retry StoryGraph requests after yielding briefly to KOReader's UI when a subprocess is dismissed, so the same tap doesn't immediately cancel the retry too.


---

Full changelog: [CHANGELOG.md](https://github.com/Lyfts/ShelfSync/blob/main/CHANGELOG.md#185)

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
