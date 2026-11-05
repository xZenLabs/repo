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

# v0.2.3 · 2026-11-04

## Added

- *Kindle browser check* (Kindles only): *Search → Settings → MDict dictionaries → Kindle browser check*. Kindle firmware 5.16.4 and later ships a Chromium browser, which could lay out entries the way the WebView does on Android: vertical Japanese, flexbox and grid, and buttons that open sections. Before that renderer is built, this check finds out whether a Kindle has the browser and enough free memory with KOReader running. It only reads system information (memory, CPU, firmware version, which of Amazon's services are running, the browser's files). It starts nothing, changes nothing, and holds no serial numbers or account names. The report is shown and saved as `koreader/mdict-kindle-report.txt`: Kindle owners, please attach it to a GitHub issue.

## Fixed

- Content that a dictionary hangs just outside its lines, such as LDELC's sense numbers, was cut off at the left edge of the page, and a sliver of it showed at the right edge of the page before. Horizontal pages now keep a small gutter on each side (4 px, scaled with the text size). Vertical entries are unchanged.
- *My font* did not apply to bold and italic text when the chosen font has no bold or italic file (KOReader's FreeSerif, for example): that text kept the dictionary's font and could lose its weight. It now uses the chosen font, made bold or slanted by the WebView, as KOReader does in books.

## Install

- From 0.2.0: *Search → Settings → MDict dictionaries → Updates → Check for updates*, or wait for the automatic offer. Then restart KOReader (on Android, exit KOReader and open it again).
- From 0.1.0: unzip `mdict.koplugin-0.2.3.zip` into `koreader/plugins/`, replacing the `mdict.koplugin` folder, and restart KOReader.

# v0.2.2 · 2026-11-03

## Fixed

- On Kindle, Kobo, PocketBook and other devices without the WebView (and on Android with the WebView turned off), entries were shown with none of the dictionary's styling, so every dictionary looked the same ([#1](https://github.com/moopoint-dev/mdict.koplugin/issues/1)). KOReader's renderer (MuPDF) reads stylesheets only from a page's head, and the entry's stylesheet links never got there. The plugin now gives the popup each entry's CSS itself, and scales sizes set in pixels to the popup's text size, since MuPDF draws a CSS pixel as one screen pixel. Layouts still look as MuPDF can draw them: no flexbox or grid, vertical text, scripts or audio.
- In dictionaries that keep each entry under a record number and link the words to it, the popup showed that number (such as `OKG1121512`) instead of the word. It now shows the entry's headword.

## Install

- From 0.2.0: *Search → Settings → MDict dictionaries → Updates → Check for updates*, or wait for the automatic offer. Then restart KOReader (on Android, exit KOReader and open it again).
- From 0.1.0: unzip `mdict.koplugin-0.2.2.zip` into `koreader/plugins/`, replacing the `mdict.koplugin` folder, and restart KOReader.

# v0.2.1 · 2026-11-03

## Fixed

- Entries could not be paged in dictionaries whose CSS restyles every `div`, such as Encarta 2009, which makes them all inline: swiping moved the page bar, but the entry stayed on its first page. The pager's own boxes are no longer divs, so a dictionary's CSS no longer reaches them. Its `div` rules now apply only to the entry's own markup, as in a dictionary app.

## Install

- From 0.2.0: *Search → Settings → MDict dictionaries → Updates → Check for updates*, or wait for the automatic offer. Then restart KOReader (on Android, exit KOReader and open it again).
- From 0.1.0: unzip `mdict.koplugin-0.2.1.zip` into `koreader/plugins/`, replacing the `mdict.koplugin` folder, and restart KOReader.

# v0.2.0 · 2026-11-02

The plugin now updates itself: it can check for new releases, download them and install them.

## New

- *Search → Settings → MDict dictionaries → Updates* shows the installed version and has *Check for updates*.
- Automatic checks, at most once a day, offer each new version when it comes out. They only run when the device is already connected (Wi-Fi is never turned on for them), stay silent otherwise, and can be turned off with *Check for updates automatically*. An offer can be skipped for that version.
- An update is checked against the size and SHA-256 that GitHub lists, unpacked next to the plugin, and moved in when KOReader next starts, so the running plugin is never half updated. After the restart, a notification says which version is now installed.

## Install

This is the first version that can update itself, so install it by hand once:

1. Unzip `mdict.koplugin-0.2.0.zip` into `koreader/plugins/`, replacing the `mdict.koplugin` folder.
2. Restart KOReader.

Later versions install from the plugin's menu. On Android, restart by exiting KOReader and opening it again.
