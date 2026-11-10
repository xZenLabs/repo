# v0.3.0 · 2026-11-10

## Faster

- Looking a word up in many dictionaries is much faster. Searching a dictionary's own key order normalised every key of each block it read; it now normalises only the dozen keys a search looks at. With 48 dictionaries on a Clear7, the search went from 0.45–0.8 s to 0.03–0.12 s per lookup.
- The first lookup after KOReader starts no longer opens every dictionary again: the dictionaries opened at start stay open (with 48 dictionaries on a Clear7, 3.3 s → 0.14 s). Small dictionaries are no longer indexed in memory again in every session: their key order is remembered, or an index is built for them once in the background.
- On WebViews older than Chromium 125 (such as WebView 109 on Android 14 e-readers), stylesheets that use CSS `round()` are rewritten once and saved, instead of in every lookup. For a dictionary with a 1.6 MB stylesheet, that is about 0.9 s less per lookup on a Clear7.
- Pronunciation links play at once. The first tap on one could wait seconds while the next result was being laid out ahead.

## Fixed

- An entry that took longer than 8 s to lay out (for example one whose embedded fonts were being extracted for the first time) made every later entry of the session use the built-in renderer (MuPDF). Time spent extracting resources no longer counts, and the WebView is given up only when two entries in a row time out.
- When MuPDF showed MDict results, every result of a lookup was prepared before the popup opened, extracting every resource its dictionary's stylesheets name. With dictionaries that embed font subsets (thousands of `@font-face` rules with a `unicode-range`), this could extract hundreds of MB, use over 1 GB of memory and leave KOReader unresponsive. Results are now prepared one at a time when shown, and MuPDF, which cannot use such subsets, no longer gets them.
- A tap a few pixels beside a small link, such as a pronunciation icon, turned the page or moved to another result. A tap within 2.5 mm of a link now opens it.
- KOReader's "Searching dictionary for…" message did not appear while MDict dictionaries were searched or the first entry was laid out, so a slow lookup looked like KOReader had stopped responding. It now appears when a lookup takes more than half a second.

## Install

- From 0.2.0: *Search → Settings → MDict dictionaries → Updates → Check for updates*, or wait for the automatic offer. Then restart KOReader (on Android, exit KOReader and open it again).
- From 0.1.0: unzip `mdict.koplugin-0.3.0.zip` into `koreader/plugins/`, replacing the `mdict.koplugin` folder, and restart KOReader.

# v0.2.11 · 2026-11-08

## Fixed

- *My font* did not reach all text. It stood in only for the fonts a dictionary's stylesheet names, so text the dictionary sets in a generic font (serif, sans-serif, system-ui, ui-serif) or in a font that only the entry's own styles name kept the dictionary's font. In a dictionary whose text is set in ui-serif, only the sense numbers and labels changed. My font now covers that text too, and the characters it has no glyphs for keep the dictionary's fonts. (#3)
- Text set in ui-serif, ui-sans-serif, ui-monospace or ui-rounded, as in dictionaries made from macOS ones, was drawn in the WebView's default font (sans-serif on Android), which does not know these names. It is now drawn in serif, sans-serif or monospace, as the dictionary intends. (#3)

## Install

- From 0.2.0: *Search → Settings → MDict dictionaries → Updates → Check for updates*, or wait for the automatic offer. Then restart KOReader (on Android, exit KOReader and open it again).
- From 0.1.0: unzip `mdict.koplugin-0.2.11.zip` into `koreader/plugins/`, replacing the `mdict.koplugin` folder, and restart KOReader.

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
