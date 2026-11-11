# v0.4.1 · 2026-11-11

## Fixed

- **E-ink mode keeps the backgrounds that carry something.** E-ink mode drew all text black and removed every background, so a caption drawn on a coloured tab over its box's border showed the border running through its text, and reversed labels (white numbers or headings on a dark background) turned into plain text. Now a dark background turns black under white text, and an opaque light one turns white, so it still covers what it covered. See-through tints go as before. Pages without such backgrounds look exactly as before.
- **No more page for a line or two at the end of an entry.** An entry that ends with space below its last lines (a margin meant for a desktop window) could have its last lines moved to a page of their own, to make room for that space. The space after an entry's last lines is now dropped where nothing is drawn around it.
- **Pronunciation buttons sit where the dictionary puts them.** Entries' `sound://` links were renamed for KOReader, so a dictionary's own rules for its sound links (`a[href^="sound://"]`) no longer applied, and a play button the dictionary aligns with its text sat below the line. The links now stay `sound://` and play as before.
- Parts of a line with a black (or yellow) background could lose it when the layout split the line around blocks. Such colours were taken for "no background".
- A dictionary's prebuilt `.koidx` index is checked again when a volume is replaced by a new copy of the same size. Some devices keep reporting the old file's date after a copy, and the plugin could then trust its earlier check of the old file without checking the index again. Each check now also records the volume's key count and key-section length and the index's header checksum, and holds only while they still match.

## For dictionary makers

`koidx-0.4.1.zip` holds the same `koidx.py` as 0.4.0.

## Install

- From 0.2.0: *Search → Settings → MDict dictionaries → Updates → Check for updates*, or wait for the automatic offer. Then restart KOReader (on Android, exit KOReader and open it again).
- From 0.1.0: unzip `mdict.koplugin-0.4.1.zip` into `koreader/plugins/`, replacing the `mdict.koplugin` folder, and restart KOReader.

# v0.4.0 · 2026-11-10

## New: dictionaries can come with their index

Most MDict files keep their keys in MdxBuilder's order, which other apps rely on, so the plugin builds its own index for each large dictionary the first time it is used. On a slow e-reader that takes from seconds to over a minute per dictionary, and the dictionary answers "being indexed" meanwhile. With 39 large Japanese and English dictionaries on a Clear7 it was about 6 minutes after every copy.

A dictionary can now come with that index prebuilt, as a `.koidx` file next to each volume (`Name.mdx.koidx`, `Name.mdd.koidx`, …). Copy it along with the dictionary and nothing is built on the device: the plugin checks that the file belongs to the volume beside it (key count, the CRC-32 of the volume's key section and a few sampled keys) and uses it at once. The rest of the file is checked once in the background. A `.koidx` that does not fit, for example one left from an older copy of the dictionary, is ignored and the plugin builds its index as before, so a wrong file is never worse than none. *Index status* shows which dictionaries came with an index, or why one was not used.

On the Clear7 with those 39 dictionaries (98 files), checking every index took about a minute and a half in the background, instead of an estimated 10 minutes of building.

## For dictionary makers

`koidx-0.4.0.zip` holds `koidx.py`, which builds `.koidx` files on a computer (Python 3.8 or later, nothing to install). It reads only each volume's header and key section, and writes exactly the index the plugin would build. Your MDict files are not changed, so other apps are not affected.

    python3 koidx/koidx.py build Name.mdx Name.mdd Name.1.mdd
    python3 koidx/koidx.py check Name.mdx

See *Dictionary exporters* in the README for details.

## Fixed

- After a dictionary's `.mdd` files were replaced with a newer copy, entries could still use stylesheets, fonts and images taken from the old files until *Clear extracted resources* was used. They are now taken again from the new files.

## Install

- From 0.2.0: *Search → Settings → MDict dictionaries → Updates → Check for updates*, or wait for the automatic offer. Then restart KOReader (on Android, exit KOReader and open it again).
- From 0.1.0: unzip `mdict.koplugin-0.4.0.zip` into `koreader/plugins/`, replacing the `mdict.koplugin` folder, and restart KOReader.

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
