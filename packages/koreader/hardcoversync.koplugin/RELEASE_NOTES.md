# v2.4.0 · 2026-11-09

## ✨ New
- Add screenshot and versioning rules to CLAUDE.md (#202)
- Add a plus FAB to the book's journal (#201)
- Add offline caching for browsed reviews (#208)
- Add changelog entries for the bug fixes (#220)
- Add changelog entries for the third round of fixes (#258)
- Add a month filter to Stats (#246)
- Add six Hardcover data cards to the Bookshelf module pack (#280)
- Save bulk-link results once per batch instead of once per book (#287)
- Add read:lists and read:goals to sign-in, and check sign-in scopes against Hardcover's scope map (#284)

## 🎨 Improved
- Make the book details buttons smaller again (#200)
- Show days from start to finish on Stats (#259)
- Show pages per month on Stats (#257)
- Show a settings row's full help text when it is held (#260)
- Show rating against length and average rating by year on Stats (#261)
- Show pages read offline in the Journal (#278)
- Improve bulk link by reading an EPUB's OPF with one unzip process (#285)
- Improve page turns on a shelf with a local search active (#286)
- Improve Reviews and Stats redraws by laying the page out once (#292)
- Improve Bookshelf card speed by building each card once per fit (#291)
- Improve eviction to check only books that may have lost their hold (#290)

## 🐛 Fixes
- Fix "Start reading this book?" never appearing when tracking is off (#205)
- Fix the empty Currently reading card on Home when offline (#203)
- Fix offline Paused status stuck after reading (#206)
- Send pages read offline with the time they were read (#207)
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
- Fix sync conflicts when opening a book and the doubled jump question (#271)
- Fix goal target input, accents in search, year 0 and offline wording (#272)
- Fix opening a book without reading resetting Hardcover's page, and the notice covering the conflict question (#273)
- Fix offline status ordering, date queued changes, and show waiting status changes in the Journal (#275)
- Fix Stats Genres ring dropping its 5th genre into Other (#274)
- Fix empty book journal cache hiding saved entries (#282)
- Fix rate-limit waits to use Retry-After and stop treating every 403 as a missing scope (#283)
- Fix vibe pagination and edition selection (#267)
- Fix cover downloads, journal pagination and Unicode search (#263)
- Fix finish dates when old read books sync offline (#294)

## 🛠 For developers
- Fix emulator scenarios failing on the sync queue's statusOf (#266)
- Fix CI Lua installation timeouts (#293)

## Other
- Turn the Library's Activity tab into your Journal (#199)
- Offer to jump to Hardcover's page when it is further along (#204)
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
- Keep the progress queue by Hardcover book instead of by file (#276)
- Keep shelf changes in the progress queue and remove the shelf queue (#277)
- Keep offline reading history ordered and safe to retry (#279)
- Adapt Bookshelf totals to portrait cards (#281)
- Batch the library lookups when the sync queue flushes (#289)
- Combine Home's reading, lists and goals requests into one (#288)
- Steer Bookshelf Sources wiki documentation (#295)
- Clarify Bookshelf sign-out wiki note (#296)
- Document PR inspection tools (#297)

**Full changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v2.3.1...v2.4.0

# v2.3.1 · 2026-10-22

## ✨ New
- Add the Paused reading status (#169)
- Correction dialog when a book is auto-linked (#175)
- Make the journal entry a themed form (#172)
- Settings gear in the reader panel (#168)
- Book search opens as a search bar in the top bar (#176)
- Add one-step stable releases with vX.Y.Z-stable (#185)
- Add the activity feed's data layer: status changes, notes, quotes and reviews (#186)
- Add an Activity tab to the Library (#188)
- Add a Journal button to the reader panel (#192)

## 🎨 Improved
- Show the books behind a book-count goal (#166)
- Move automatic tracking into the set-page dialog (#171)
- Book details: every action is a button (#194)
- Rework the reader panel with fixed actions and top controls (#196)
- Show release notes in a fixed scrollable Markdown dialog (#198)

## 🐛 Fixes
- Fix scrolling stalling mid-page (#177)

## 🛠 For developers
- Run the emulator at three screen sizes with layout checks (#178)
- Hold emulator fixtures to the shape of the real API (#173)
- Add Theme.* ratchet harness (#174)
- Verify journal, review and activity API against Hardcover (#170)

## Other
- Number picker: type the value, dotted buttons at the ends, hold to repeat (#179)
- Notes and quotes save offline and send later (#180)
- Group release notes by category automatically (#181)
- Write your review from the book details, offline too (#183)
- Design docs for the e-reader target; dialogs 80% wide with side-by-side buttons (#182)
- Dialogs about 80% wide with side-by-side buttons (#187)
- Update the design docs to leave sheets as they are (#189)
- Keep Activity on the device and show what is waiting to send (#190)
- Let you edit and delete your notes, quotes and reviews from Activity (#193)
- Download new covers three at a time (#184)
- Balance the reader panel and restore readable book actions (#197)

**Full changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v2.2.0...v2.3.1

# v2.2.0 · 2026-10-21

This release gives the plugin's dialogs and messages a consistent new look, and fixes finish dates for books finished offline.

## ✨ New
- **Updated dialogs:** Dialog now follows the MMD spec (#162). It and Snackbar replace the old ConfirmBox and InfoMessage, plus some toasts (#163).
- **Progress dialog with a visible Stop button** (#164)
- New UI components: a themed input dialog (#165), plus a number stepper and a date picker (#167)

## 🐛 Fixes
- When a finish made offline is synced, its finish date is now sent too (#161)

**Full Changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v2.1.0...v2.2.0

## What's Changed
* Bring Dialog to the MMD spec by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/162
* Replace ConfirmBox, InfoMessage and some toasts with Dialog and Snackbar by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/163
* Send the finish date when a finish made offline is synced by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/161
* Add a progress dialog with a visible Stop by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/164
* Add a themed input dialog by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/165
* Add a number stepper and a date picker by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/167


**Full Changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v2.1.0...v2.2.0

# v2.1.0 · 2026-10-21

Bulk linking is the big change in this release: link every book on your device in one go, and get guesses for books that don't match exactly.

✨ **New**
Link all books on this device, 25 at a time (#149). Details and shelves are saved afterwards (#153).
Guess unmatched books from title and author, then review the guesses before they're applied (#154)
Hardcover details button in the file dialog (#142)
Goal and stats cards for Bookshelf micro-modules (#151)
Set a page by hand on a book set to Reading while offline (#145)
New UI components: button sizes, a round button and a floating action button (#157, #158)
🐛 **Fixes**
Progress is now sent to the read Hardcover already has (#147)
Book details no longer does the cover work twice or runs full refreshes when it opens (#141)
Lists now page correctly while covers are loading (#155, #159)
"Add to lists" changes are applied when you press Done (#160)
🛠 **For developers**
Install from branch: new developer option (#143)


## What's Changed
* Run the emulator scenarios in CI by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/140
* Hardcover details button in the file dialog by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/142
* Install from branch (developer option) by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/143
* Book details: fix doubled cover work and full refreshes on open by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/141
* Emulator: un-park the two offline scenarios by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/144
* Add a nightly live check against the real Hardcover API by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/146
* Send progress to the read Hardcover already has by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/147
* Allow setting a page by hand on a book set to Reading offline by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/145
* Emulator: fix the last three parked scenarios by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/148
* Link all books on this device, 25 at a time by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/149
* Tests: one shared check helper, totals in run_all, a spec README by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/150
* Lint with luacheck in CI by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/152
* Save details and shelves after "Link all books" by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/153
* Hardcover goal and stats cards for Bookshelf micro-modules by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/151
* Snackbar passthrough and list paging while covers load (for testing together) by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/159
* Fix lists not paging while covers load by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/155
* Button sizes and a round button by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/157
* Apply Add to lists changes when Done is pressed by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/160
* Guess unmatched books from title and author, and review the guesses by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/154
* Floating action button component by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/158


**Full Changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v2.0.0...v2.1.0

# v2.0.0 · 2026-10-13

## What's Changed
* Split DialogManager: pure loaders and decision modules for Home, Shelf, Lists and Goals by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/40
* Keep open screens in a registry and remove the unused done_callback by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/41
* Fix Scheduler:clear(), which cancelled no retry loops by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/42
* Give the three offline queues a shared base by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/43
* Extract the book details flows from DialogManager by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/44
* Make charts' atan2 work on Lua 5.3+ as well as LuaJIT by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/45
* API layer: generate async wrappers, move the UI and HTTP out of hardcover_api by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/46
* Fix stale emulator reviews scenario (spoiler is on page 2) by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/47
* Bring 1.6.3-beta.3 into main: update-check fixes and changelog by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/48
* Order hardcover_api.lua by area, async wrappers last by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/49
* Release 1.6.3 by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/50
* theme.lua: pill buttons, serif headings, solid black progress bars, hatching and icon helpers by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/51
* Bundle plugin icons by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/52
* Beta 1.7.0-beta.1: lists kept on the device by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/54
* Beta 1.7.0-beta.2: shelves, book details and covers kept on the device by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/56
* Fix list covers drawn too small or spilling out of their row by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/58
* Sharper covers: details at their exact size and quality 90, all covers dithered by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/59
* Lists kept on the device: offline, and downloaded only when they change by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/53
* Shelves, book details and covers kept on the device (stacked on #53) by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/57
* Release 1.7.0 by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/60
* Sync beta with main after 1.7.0 by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/61
* Stats: a genres donut, a Pace line for a year, and a range for book length by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/73
* MMD design overhaul on the beta, nav bar indicator at the bottom by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/74
* Scroll control on every long screen by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/62
* Design tokens: secondary text setting, dotted rule, MMD metrics by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/63
* Ship Lato and install it into KOReader's fonts folder by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/65
* Merge main into beta after the 2.0.0 betas by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/75
* Merge beta into main (move to trunk-based) by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/76
* Hardcover shelves and lists as Bookshelf sources by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/78
* Scroll control: rounded track, inset bar by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/79
* Setting to choose the book search plugin by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/80
* Shelf and list changes work offline by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/83
* Settings: grouped options with folding headings by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/81
* Reader sheet: Change status; radios for single choices in Settings by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/82
* Publish any tag containing beta as a pre-release by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/84
* Number betas automatically when a beta is typed without one by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/85
* Bookshelf sources: make sorting work by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/89
* Leave Finished and Did not finish books alone at the end of a book by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/90
* Archive goals from the goal screen, offline too by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/86
* Bookshelf: cheaper shelf sorting on slow devices by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/92
* Reading a Want to Read or unshelved book puts it on Currently Reading by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/93
* Answer user actions with the snackbar by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/97
* No grey for unavailable buttons and rules by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/101
* MMD search field for Home and search results by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/103
* One MMD chip for goal and shelf state by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/105
* Docs: which MMD components are used, and why the rest are not by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/107
* docs: Home shows one reading card by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/100
* No goals reads the same saved or fresh by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/99
* Drop Bookshelf's shelves only when a book's status really changes by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/98
* Shape shelf rows only for the page on screen by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/102
* Home's Sync now works in every language by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/94
* A tab that fails to load says so instead of loading for good by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/95
* Sync opens the pending changes; Home's sync box opens them too by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/87
* Shelf counts on Home and Shelves follow a moved book by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/96
* Bookshelf: open a saved shelf without decoding every book by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/108
* Bookshelf: open a saved list without decoding every book by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/109
* perf_screens: reader panel fixture and budget match the real sheet by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/112
* Stretch shelf rows to fill the page by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/111
* perf_home: allow 4 full-panel refreshes on the cold open by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/115
* Emulator scenarios: skip the snackbar when finding the top window by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/114
* book_rating scenario: hold the dialog the call returns, skip unnamed windows by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/117
* Reader panel: where the book is and how far, Read again beside it by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/110
* Ask before starting to track a book that is not Currently Reading by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/113
* Emulator: wipe the screen between scenario cases by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/118
* Search results: flash the panel as they appear so covers do not ghost on Home by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/119
* Scroll bar: hold the up or down triangle to jump to the start or end by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/120
* Book and edition pickers on the shelf screen by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/121
* Change a linked book's edition from the reader panel by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/122
* One Add button replaces Shelf and Lists on the book details screen by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/123
* Edition button on the book details screen by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/124
* Reader panel: look the book up in the saved shelves by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/126
* Reader status changes update the saved shelves by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/127
* Fix Edition button crash on the book details screen by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/128
* Remove the old Home screen by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/129
* Book details: use the full width when the page does not scroll by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/131
* Open the home screen with a full refresh by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/130
* Home: fit the Read shelf on a small screen by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/125
* Fix offline Currently Reading shelf after cancel and for uncached books by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/133
* Open every full-screen screen with a full refresh by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/134
* Release 2.0.0 by @CaptainCamin in https://github.com/CaptainCamin/HardcoverSync.koplugin/pull/132


**Full Changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v1.6.2...v2.0.0
