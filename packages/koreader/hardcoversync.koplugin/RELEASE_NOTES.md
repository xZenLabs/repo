# v2.5.1 · 2026-11-19

## 🐛 Fixes
- Fix low-priority UI consistency and layout issues 
- Fix the two data-loss edges 

**Full changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v2.5.0...v2.5.1

# v2.5.0 · 2026-11-18

## ✨ New
- Add reading history, layout A details and offline read edits (#306)
- Add new-install defaults and fix rating and note privacy (#328)
- Add Abandon reread to reading history (#329)

## 🐛 Fixes
- Fix edition lookup crash on partial reads response (#299)
- Fix reading state refresh after saves (#320)
- Fix status menu book removal confirmation (#322)
- Fix the date picker's drifting month and year controls (#325)
- Fix removal confirmation to say journal entries stay on Hardcover (#330)
- Fix review scope, held-change UX, and signed-out Home (#323)
- Fix reviews histogram label collision (#324)

## 🛠 For developers
- Gate emulator CI behind path and skip checks (#298)
- Fix read history emulator date check (#326)

## Other
- Share Bookshelf module plugin lookup (#302)
- Consolidate shallow table copies (#303)
- Share text trimming and local search filtering (#304)
- Park sync conflicts and recheck library removals (#305)
- Queue shelf changes when Hardcover does not answer (#319)

**Full changelog**: https://github.com/CaptainCamin/HardcoverSync.koplugin/compare/v2.4.0...v2.5.0

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
