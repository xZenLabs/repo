# v2.4.0-beta.5 · 2026-10-30

## ✨ New
- Add changelog entries for the bug fixes (#220)
- Add changelog entries for the third round of fixes (#258)
- Add a month filter to Stats (#246)

## 🎨 Improved
- Show days from start to finish on Stats (#259)
- Show pages per month on Stats (#257)
- Show a settings row's full help text when it is held (#260)
- Show rating against length and average rating by year on Stats (#261)

## 🐛 Fixes
- Fix a newer journal edit being lost while an older one is sent (#210)
- Fix book details showing another edition's data while online (#212)
- Fix an existing review opening blank after a cached reopen (#213)
- Fix progress updates using the wrong read after changing edition (#214)
- Fix choosing Private leaving an existing book Public (#215)
- Fix "Jump to Hardcover's page" ignoring the book's page labels (#216)
- Fix sign-in forgetting the server's polling backoff (#217)
- Fix restarting bypassing refresh-token replay protection (#218)
- Fix Charts.decimal stripping real zeros with zero places (#222)
- Fix the GraphQL query for looking up a book by edition id (#223)
- Fix Charts.niceScale giving a step of 3 (#224)
- Fix a stale read and edition surviving a book snapshot that has none (#225)
- Fix goal dates like 2026-02-31 being accepted (#227)
- Fix Charts.number showing -0 and exponent notation (#228)
- Fix review excerpts and chart labels counting bytes instead of characters (#232)
- Fix Link all books dropping urn:isbn identifiers without a scheme (#233)
- Fix journal times with a zone offset that has no minutes (#234)
- Fix accented initials sorting after Z in shelf title and author sort (#235)
- Fix early pages mapping to page 0 when the file is longer than the edition (#239)
- Fix books fetched for a list or shelf download being evicted when a book is opened (#242)
- Stop an overlapping sync from reporting a failure (#243)
- Fix download queue keys shared between accounts (#245)
- Fix cancelled goals and journal notes still being sent (#211)
- Fix book lookup to try the ISBN-10 after the ISBN-13 (#226)
- Fix a crash sorting goals with mixed local and server ids (#230)
- Fix ISBN-10s ending in X never being parsed (#236)
- Fix a queued reader status being reverted when the book's details open online (#244)
- Fix a crash in findDefaultEdition when the book is missing (#229)
- Apply a changed tracking frequency without a restart (#247)
- Stop a retried re-read from creating a read each time (#248)
- Send the last page before marking a book Finished (#254)
- Fix offline status chains losing Currently Reading, and finish-then-restart (#262)
- Fix bulk link missing the identifier after an empty identifier element (#221)
- Fix end-of-book prompt after a re-read and goal archived mid-send (#219)
- Fix list and shelf changes lost when undone while being sent (#264)
- Fix a discarded note still reaching Hardcover when discarded mid-send (#265)
- Fix closing a book, zero-page editions, backward jumps and the doubled end-of-book dialog (#268)
- Fix sent journal entries, note pages and book journals offline (#269)
- Fix ratings marking books as Read, Read again adding an empty read, and the current read (#270)

## 🛠 For developers
- Fix emulator scenarios failing on the sync queue's statusOf (#266)

## Other
- Scope offline goal changes to the account that made them (#231)
- Keep offline shelf moves and removals when an earlier download finishes (#237)
- Hide another account's waiting shelf change (#238)
- Retry queued changes after an expired token or timeout (#240)
- Keep offline list adds and removals when an earlier download finishes (#241)
- Ignore the Link, Track and Stop tracking gestures when no book is open (#249)
- Clear queued entries without a timestamp once they are sent (#250)
- Keep the inherited tracking default when setting the page without touching the toggle (#251)
- Drop the older queued page when a book is marked Finished online (#252)
- Do not send one account's offline reading to the next account (#253)
- Refresh the Settings screen when sign-in succeeds (#255)
- Report an error when an approved sign-in holds no usable tokens (#256)

**Full changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v2.4.0-beta.4...v2.4.0-beta.5

# v2.4.0-beta.4 · 2026-10-29

## ✨ New
- Finishing a book now reaches Hardcover (#209)
  - Switching a book to Finished on KOReader's book-status screen is sent to Hardcover when the screen closes. It used to be missed.
  - Staying on the last page for 20 seconds asks "Mark as Read?", once per book per session. A new setting, "Mark as Read automatically on the last page", skips the question. The question is off by default when another end page (Hardcover's or ZenOS's) is chosen, and has its own setting.
  - A new "Hardcover end page" choice in KOReader's End of document action list shows the book, its status, your rating, a review link and Mark as Read. Offline, the change waits in Pending changes.
  - Read is never overwritten, and Did not finish still asks first.

## 🛠 For developers
- Run the emulator on KOReader 2026.07.1 (#209)
- Fold the Tracking section too in the settings emulator scenario

Not yet tried on a device: the new hooks into KOReader's book-status screen and End of document action menu. If either misbehaves, please report it.

**Full changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v2.4.0-beta.3...v2.4.0-beta.4

# v2.4.0-beta.3 · 2026-10-28

No pull requests were merged since the last release.

**Full changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v2.4.0-beta.2...v2.4.0-beta.3

# v2.4.0-beta.2 · 2026-10-28

No pull requests were merged since the last release.

**Full changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v2.4.0-beta.1...v2.4.0-beta.2

# v2.4.0-beta.1 · 2026-10-25

Browse community reviews even when you are offline. Pages you have opened, including their full text and your place in the list, stay on this device; spoiler protection stays in place, and a later refresh replaces the saved copy only when it succeeds.

## ✨ New

- **Reviews you have opened work offline.** Your saved pages keep their text, spoilers and place in the list. A partial saved list says so clearly, and a failed refresh never removes what you can already read. (#208)
- **Add to a book’s journal from the reader.** The Journal screen now has a plus button for a note, quote or review. It works offline, appears in the list immediately and reuses the existing forms. (#201)
- **Journal replaces Activity in Library.** It brings together progress, reading status, notes, quotes and reviews, with your pending offline entries first. (#199)
- **Jump to Hardcover’s newer page.** When Hardcover is at least five pages ahead, you can jump there instead of working out the page yourself. (#204)

## 🎨 Improved

- **Book details fit comfortably again.** The round actions and their labels are smaller, and Open / Find on device has its normal height. (#200)

## 🐛 Fixes

- **Starting a book is prompted reliably.** “Start reading this book?” now appears even while automatic progress tracking is off. (#205)
- **Offline Home stays accurate.** Currently Reading no longer disappears from Home when you are offline. (#203)
- **Paused books stay paused.** Reading while offline no longer leaves a book stuck in the wrong status after it is synced. (#206)
- **Offline reading keeps its real dates.** Pages read across several days are sent as dated daily progress entries, rather than all appearing on the reconnect day. (#207)

**Full changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v2.3.1...v2.4.0-beta.1
