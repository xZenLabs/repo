# v0.2.10 · 2026-11-07

## Changed

- An audio player in an entry now shows that it is playing: a tap on it turns its play button into a stop button, and its time and progress bar follow the recording (on e-ink, only the player's area is refreshed, once a second). A tap on the stop button stops the recording.
- A recording played from a result stops when you move to another result, look a word up from it, or close the popup. This applies to speaker icons as well as players.

## Install

- From 0.2.0: *Search → Settings → MDict dictionaries → Updates → Check for updates*, or wait for the automatic offer. Then restart KOReader (on Android, exit KOReader and open it again).
- From 0.1.0: unzip `mdict.koplugin-0.2.10.zip` into `koreader/plugins/`, replacing the `mdict.koplugin` folder, and restart KOReader.

# v0.2.9 · 2026-11-07

## Fixed

- Lines drawn over each other: dictionaries whose CSS uses `round()` (for example to set line heights) showed every line of an entry on top of the one before in WebViews older than Chromium 125, which many e-readers have. On such a WebView, these stylesheets are now rewritten without `round()`.
- Audio players in entries (`<audio controls>`, such as a "read the definition" player at the end of an entry) did nothing when tapped. A tap now plays the recording, as speaker icons do, and so does a button whose script plays a sound.

## Changed

- A recording that a dictionary only links on the web (its .mdd has no copy) is downloaded when you tap it, once KOReader is online, and kept for the next time.

## Install

- From 0.2.0: *Search → Settings → MDict dictionaries → Updates → Check for updates*, or wait for the automatic offer. Then restart KOReader (on Android, exit KOReader and open it again).
- From 0.1.0: unzip `mdict.koplugin-0.2.9.zip` into `koreader/plugins/`, replacing the `mdict.koplugin` folder, and restart KOReader.

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
