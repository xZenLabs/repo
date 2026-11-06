# v0.2.8 · 2026-11-06

## Changed

- Kindle's browser (experimental): switching to an MDict result in the popup is faster. The browser lays out one entry at a time, so before, an MDict result was only laid out once it was shown, and again each time you came back to it. Now, while another dictionary's result is shown, the nearest MDict result is prepared in the background, and the MDict result you move away from is kept, so that going back to it is immediate. (#1)
- E-ink screens: entry pages are kept in grey, which takes a quarter of the memory. This matters most on Kindles, where the browser and KOReader share little memory.
- Kindle's browser: the log (`crash.log`) now also records what the system says about the e-ink screen's controller, a moment after each entry is shown. This should tell whether pages that stay half drawn on page turns come from the screen controller. (#1)

## Fixed

- Links to a place in the same entry (`entry://#…`, used for buttons that jump to a section) did nothing: they were looked up as an empty word. They now go to the page of that place. Buttons whose script scrolls to a section now go to that section's page too. (#1)

## Install

- From 0.2.0: *Search → Settings → MDict dictionaries → Updates → Check for updates*, or wait for the automatic offer. Then restart KOReader (on Android, exit KOReader and open it again).
- From 0.1.0: unzip `mdict.koplugin-0.2.8.zip` into `koreader/plugins/`, replacing the `mdict.koplugin` folder, and restart KOReader.

# v0.2.7 · 2026-11-06

## Added

- *Flash the screen on page turns* (e-ink screens, off by default): *Search → Settings → MDict dictionaries → Display*. Each page turn in an entry then fully refreshes the popup, which clears the ghosts of earlier pages that e-ink screens can leave, at the cost of a flash. Without it, page turns refresh the screen as KOReader's own dictionary popup does, with a flash only every few refreshes. (#1)

## Changed

- Kindle's browser (experimental): when memory runs low, the browser is asked to free its caches, and if that is not enough, it is closed and entries are shown with KOReader's renderer, with a note that the Kindle is low on memory. Before, the Kindle could freeze for half a minute until the system ended the browser itself. (#1)
- Kindle's browser: if the system ends the browser because memory ran out, the note now says so instead of "killed by signal 9".
- Kindle's browser: the log (`crash.log`) now gives the memory available with each entry, which helps with reports.
- Updates: a download that stalls is tried again, up to three times, with more time each try, and a failed download says where to get the release by hand. Timeouts are described in words on older KOReader versions instead of "wantread". (#1)

## Fixed

- A warning from the WebView renderer wrote a block of internal text into the log before the message.

## Install

- From 0.2.0: *Search → Settings → MDict dictionaries → Updates → Check for updates*, or wait for the automatic offer. Then restart KOReader (on Android, exit KOReader and open it again).
- From 0.1.0: unzip `mdict.koplugin-0.2.7.zip` into `koreader/plugins/`, replacing the `mdict.koplugin` folder, and restart KOReader.

# v0.2.6 · 2026-11-06

## Fixed

- At a text size other than 100 %, Android WebViews older than Chromium 128 (and the Kindle's browser) got the position of everything in an entry wrong by the text size. Opening a section jumped back several pages, a tap on a link could miss it and turn the page instead, and *Find* matches and the selection box were drawn in the wrong place. (#2)
- A tap on part of an entry that runs over two pages (such as a definition that shows its translation when tapped) went back to the page where that part starts. It now stays on the page tapped.
- Sections that open and close with a checkbox and no script also turned the page, and the entry was not laid out again.

## Install

- From 0.2.0: *Search → Settings → MDict dictionaries → Updates → Check for updates*, or wait for the automatic offer. Then restart KOReader (on Android, exit KOReader and open it again).
- From 0.1.0: unzip `mdict.koplugin-0.2.6.zip` into `koreader/plugins/`, replacing the `mdict.koplugin` folder, and restart KOReader.

# v0.2.5 · 2026-11-05

## Added

- *Render entries with the Kindle's browser (experimental)* (Kindles only, off by default): *Search → Settings → MDict dictionaries → Display*. Entries are laid out by the web browser that the Kindle's firmware ships (5.16 to 5.18, which runs it in Amazon's `/chroot`), as the WebView does on Android: with the dictionary's own CSS, vertical text, and the entry's scripts (sections that open and close, picture viewers). The first lookup starts the browser, which takes about 20 seconds on a Paperwhite 4; a message says so. It then stays open for the next lookups, also while the Kindle sleeps, and is closed after twenty minutes without one. It uses about 70 MB of memory, and starts only when 80 MB are free. Its window stays off the screen and it is kept away from the Kindle's own software, as in the *Kindle browser test*. If the browser cannot start or ends, entries are shown with KOReader's renderer for the rest of the session, with a note saying why. Sounds do not play on Kindles. If the Kindle behaves oddly, turn the option off and restart the Kindle. Reports are welcome in a GitHub issue.

## Changed

- Dictionaries that name Hiragino, Palatino, Georgia, Verdana and similar fonts get the Kindle's own Mincho, Gothic, Bookerly and Amazon Ember fonts in the Kindle's browser.
- The *Kindle browser test* closes the browser right away instead of waiting five seconds for it.

## Fixed

- A tap on a picture viewer that an entry's script opened could fall through to the entry under it in older versions of Chromium, the Kindle's among them.

## Install

- From 0.2.0: *Search → Settings → MDict dictionaries → Updates → Check for updates*, or wait for the automatic offer. Then restart KOReader (on Android, exit KOReader and open it again).
- From 0.1.0: unzip `mdict.koplugin-0.2.5.zip` into `koreader/plugins/`, replacing the `mdict.koplugin` folder, and restart KOReader.

# v0.2.4 · 2026-11-04

## Added

- *Kindle browser test (experimental)* (Kindles only): *Search → Settings → MDict dictionaries → Kindle browser test (experimental)*. The next step toward laying out entries on Kindles with the browser that the firmware ships. It starts the Kindle's own browser once in the background, lays out two made-up sample entries (vertical Japanese and English), shows the pages the browser drew, and closes it again, reporting the time and memory each step took. It works with the browser of firmware 5.16 to 5.18, which runs in Amazon's `/chroot`, and asks before it starts. While it runs (up to about two minutes) KOReader does not respond. The browser's window stays off the screen, and the browser is kept away from the Kindle's own software: no title bar appears and nothing is added to the browser history. Everything it puts on the Kindle goes to `/tmp` and is removed afterwards. The report is saved as `koreader/mdict-kindle-browser-test.txt`, with the two pages beside it as `mdict-kindle-browser-ja.png` and `mdict-kindle-browser-en.png`: Kindle owners, please attach all three to a GitHub issue.

## Fixed

- Furigana (ruby) came apart in older versions of Chromium, the Kindle's among them: each reading was drawn as a line of its own, spread along the column. Android WebViews before version 121 lay ruby out the same way.
- Entries of dictionaries whose scripts show them only once the page has loaded, such as Chambers Dictionary 13th, were blank. The pager now runs what an entry's scripts set up for the page's DOMContentLoaded and load events, as a browser does for each page.
- A dictionary title written as a whole HTML page (现代汉语规范词典 converted on macOS, for example) showed its markup in the popup. Its text is shown now, without a rescan.
- The *Kindle browser check* showed "? free" for storage with KOReader 2026.07 and earlier.

## Install

- From 0.2.0: *Search → Settings → MDict dictionaries → Updates → Check for updates*, or wait for the automatic offer. Then restart KOReader (on Android, exit KOReader and open it again).
- From 0.1.0: unzip `mdict.koplugin-0.2.4.zip` into `koreader/plugins/`, replacing the `mdict.koplugin` folder, and restart KOReader.
