# mdict.koplugin

MDict (.mdx/.mdd) dictionaries for KOReader, shown in KOReader's own
dictionary popup next to its StarDict dictionaries. On Android, entries are
laid out by the system WebView (Chromium) and shown a page at a time, so
complex dictionary layouts keep their original look, including vertical
Japanese, and their scripts and audio work. Elsewhere, entries fall back to
KOReader's built-in HTML renderer.

## Why

KOReader looks words up in StarDict dictionaries only, and lays out HTML
definitions with MuPDF. MuPDF is a document renderer rather than a browser:

- It supports part of CSS only (no flexbox or grid), so many modern dictionary
  layouts fall apart.
- It has no vertical text (`writing-mode: vertical-rl`), so Japanese dictionaries
  that are set vertically show horizontally.
- It runs no JavaScript: collapsed sections stay closed and images can't be
  opened full size.
- KOReader plays no audio, so pronunciations and example recordings are dead links.

The usual ways around this have their own costs. Converting MDict files to
StarDict (for example with PyGlossary) drops the audio and the scripts, needs
the CSS copied by hand, and has to be redone whenever the dictionary changes.
Sending lookups to an external app (GoldenDict, Eudic, DictTango and others)
leaves KOReader on every lookup, which on e-ink means several full-screen
refreshes, and most of these apps scroll rather than turn pages.

This plugin keeps lookups in KOReader's popup, with no conversion step:

- It reads `.mdx`/`.mdd` files directly (MDict 1.2 and 2.0, zlib and LZO, encrypted
  key index), and lists them with the StarDict dictionaries in *Manage dictionaries*.
- On Android it lays entries out with the system WebView: full CSS, web fonts and
  the fonts in the `.mdd`, vertical text, ruby, tate-chu-yoko, SVG, and the
  dictionary's own scripts.
- It plays pronunciations and example recordings from the `.mdd`.
- It shows each entry a page at a time, sized to the popup, for e-ink. It works with
  KOReader's large window and with nested lookups, lookup history and the
  vocabulary builder.
- It needs no custom KOReader build: its Java side is loaded at runtime. It updates
  itself from this repository's releases.

## Screenshots

Taken on the Android emulator in `tools/emulator/` (7", 300 ppi). Pinching out
on the popup switches KOReader to its large dictionary window. In the GIFs,
grey circles mark the touches.

<table>
<tr>
<td width="50%"><img src="docs/media/oxford-ec-rabbit.png" alt="The entry for rabbit in the Oxford English-Chinese dictionary, with its illustration, in KOReader's dictionary popup"></td>
<td width="50%"><img src="docs/media/gendai-ko-stroke-order.png" alt="The kanji entry for 故 in vertical text, with a stroke-order column, ruby and upright numbers"></td>
</tr>
<tr>
<td>Horizontal: <i>rabbit</i> in an English-Chinese dictionary, with its illustration.</td>
<td>Vertical: the kanji 故, with stroke order, ruby and upright numbers (tate-chu-yoko).</td>
</tr>
<tr>
<td><img src="docs/media/daijisen-sokyokusen.png" alt="The entry for 双曲線 (hyperbola) in horizontal Japanese, with accent marks, audio buttons and a color diagram"></td>
<td><img src="docs/media/gendai-sokyokusen.png" alt="The entry for 双曲線 (hyperbola) in vertical Japanese, with two drawings of hyperbolas"></td>
</tr>
<tr>
<td>Horizontal Japanese: 双曲線, with accent marks, audio buttons and a diagram.</td>
<td>Vertical Japanese: 双曲線, with its figures.</td>
</tr>
<tr>
<td><img src="docs/media/pagination-vertical-inu.gif" alt="Looking up 犬: pinching out to the large window, turning pages, and swiping through results from three dictionaries"></td>
<td><img src="docs/media/pagination-horizontal-watch.gif" alt="Looking up watch: pinching out to the large window, opening and closing a folded section, turning pages, and opening an illustration"></td>
</tr>
<tr>
<td>犬: pages and results, from vertical entries to a horizontal one.</td>
<td><i>watch</i>: a folded section, pages, the next result, and a full-size illustration.</td>
</tr>
</table>

## Install

1. Unzip a release zip (`mdict.koplugin-<version>.zip`) into `koreader/plugins/`.
   The repository itself is not the plugin folder: from a checkout, copy its
   `mdict.koplugin/` folder instead.
2. Put dictionaries in KOReader's dictionary folder (`koreader/data/dict/`), or
   add folders under *Search → Settings → MDict dictionaries → Dictionary folders*.
   Keep each `.mdx` next to its `.mdd` files (`name.mdd`, `name.1.mdd`, ...).
3. Restart KOReader. MDict dictionaries appear in KOReader's *Manage dictionaries*
   list, where they are enabled, disabled and ordered like StarDict ones.

Large dictionaries whose keys are not in the plugin's sort order are indexed
once in the background (a few seconds each, a minute or more for the largest on
slower e-readers). Until then their lookups show a note; a notification says
when an index you were waiting for is ready. A dictionary that comes with a
prebuilt index (`name.mdx.koidx`, see *Dictionary exporters*) needs no indexing:
keep that file next to the `.mdx`.

## Reading entries

- Horizontal entries: swipe up/down or tap the right/left half to turn pages.
- Vertical (right-to-left) entries: swipe left to right, or tap the left half,
  for the next page; swipe up/down to change dictionary. The page bar runs
  along the bottom.
- Links, `#anchors` and cross references work; tapping a collapsed section
  (such as *Extra Examples*) opens it in place.
- Pinch out on the popup to switch to KOReader's large window, which fits more
  on each page.
- Hold a word to look it up; hold and drag to select. *Find in definition*
  searches the whole entry.
- Tap a speaker icon or an audio player to hear the recording (Android; AAC, MP3,
  Ogg and WAV play, Speex does not). A recording the dictionary only links on the
  web is downloaded when you tap it, once KOReader is online, and kept for the next time.
  A player shows its progress while it plays, and a tap on it stops it; moving to another
  result or closing the popup stops the recording too.

## Settings

*MDict dictionaries* in the search menu:

- **Display**: render with the WebView or KOReader's renderer (on Kindles, with the
  Kindle's own browser, see below), text size,
  e-ink mode (black text, no tinted backgrounds), your own font for all text,
  Latin text only, or Japanese/Chinese text only, reversed swipes for
  vertical text, a flash on every page turn (e-ink screens, off by default: it clears
  the ghosts of earlier pages), and preparing the next result in advance (on by default: while
  you read one result, the next MDict result is laid out in the background).
- **Dictionary settings**: per dictionary, the writing direction (automatic,
  horizontal, vertical) and page layout (columns, or slices for layouts that
  columns cut off; automatic switches when needed).
- **Dictionaries found** (or **Index status**): a full-screen list of the dictionaries,
  sorted by name, with the state of each one's index; tap one for its file, size,
  resource files and override files.
- **Rebuild indexes**, **Clear extracted resources**, **Rescan**.
- **Updates**: the installed version, *Check for updates*, and *Check for updates
  automatically* (on by default).
- **Render entries with the Kindle's browser (experimental)** (Kindles only, off by
  default, in *Display*): lays entries out with the web browser of the Kindle's
  firmware (5.16 to 5.18, Chromium 75 in Amazon's `/chroot`), as the WebView does on
  Android: the dictionary's CSS, vertical text and the entry's scripts. The first
  lookup starts the browser, which takes about 20 seconds on a Paperwhite 4; it then
  stays open, also while the Kindle sleeps, and is closed after twenty minutes without
  a lookup. Pages come from the browser's screencast (under a second each on the
  emulated Paperwhite), with a screenshot when no frame comes. The browser lays out one
  entry at a time: while another dictionary's result is shown, the nearest MDict result
  is prepared, and the MDict result you move away from is kept, so that going back to it
  is immediate. The browser uses about
  70 MB of memory and starts only when 80 MB are free. If memory runs low later, it is
  asked to free its caches, and closed if that is not enough, before the Kindle runs
  out. If it cannot start, or ends, entries fall back to KOReader's renderer for the
  session. Turn it off and restart the
  Kindle if anything misbehaves.
- **Kindle browser check** (Kindles only): a report for the Kindle renderer, about the
  browser that Kindle firmware 5.16.4 and later ships.
  It only reads system information (memory, Amazon's services, the browser's files),
  starts nothing, and saves the report as `koreader/mdict-kindle-report.txt`.
- **Kindle browser test (experimental)** (Kindles only): starts the Kindle's own
  browser once in the background, lays out two sample entries with it, and closes it
  again. It reports the time and memory this took, and shows the pages the browser
  drew. Everything it puts on the Kindle goes to `/tmp` and is removed afterwards;
  the report is saved as `koreader/mdict-kindle-browser-test.txt`, with the pages
  beside it. It supports firmware 5.16 to 5.18 for now (the browser that runs in
  Amazon's `/chroot`).

Override files, for fixes a dictionary's own CSS or markup needs on an e-reader:

- `name.koreader.css` next to `name.mdx`: extra CSS applied after the dictionary's own.
- `name.koreader.lua` next to `name.mdx`: returns a function that takes an entry's
  HTML and returns it changed, for fixes CSS cannot make. It can use the `string`,
  `table` and `math` libraries only.
- `mdict.koreader.css` and `mdict.koreader.lua` in a dictionary folder (or a folder
  inside it): the same, for every dictionary in that folder and below, for example
  all the files from one exporter. They apply before the per-dictionary files.

## Updates

The plugin updates itself from this repository's
[releases](https://github.com/moopoint-dev/mdict.koplugin/releases) (from 0.2.0 on;
install 0.2.0 by hand over 0.1.0).

- *Check for updates* asks GitHub for the latest release, turning Wi-Fi on if needed,
  and offers to install a newer one.
- Pre-releases (test builds) are never offered; install them by hand.
- Automatic checks run at most once a day: a minute after KOReader starts, when it
  connects to a network, or when the device wakes up. They only run when the device
  is already connected (Wi-Fi is never turned on for them), in the background, and
  say nothing unless there is a new version. Its offer has *Skip this version*.
- *Update* downloads the release zip (checked against the size and SHA-256 that
  GitHub lists) and unpacks it next to the plugin, as `.mdict.koplugin.update`. The
  running plugin is not touched: the new version is moved in when KOReader next
  starts, before any of the plugin's code loads. On Android, restart by exiting
  KOReader and opening it again.

Releases are tagged `v<version>`, where `<version>` is the `version` in
`mdict.koplugin/_meta.lua`, the only place it is set; `tools/release.sh` refuses
a tag or version that differs. A release needs an asset named
`mdict.koplugin-<version>.zip`.

## Limitations

- MDict 3.0 files, and registered files whose records are encrypted, are not
  supported yet.
- Speex audio does not play.
- The WebView renderer is Android only, with an experimental one on Kindles with firmware
  5.16 to 5.18 (see *Settings*). On other Kindles, Kobo, PocketBook and other
  devices, entries are laid out by KOReader's renderer (MuPDF) with the
  dictionary's CSS, as far as MuPDF supports it (no flexbox or grid). Vertical
  text, scripts (such as buttons that open or close a section) and audio do not work.
- Some dictionaries' CSS is made for color phone screens; override files (above)
  can adapt it for e-ink.

## Dictionary exporters

Most MDict files keep their keys in MdxBuilder's order, which other readers
such as DictTango rely on, so the plugin builds an index for them on the
device. Dictionary makers can build that index on a computer instead and ship
it next to each volume:

    python3 tools/koidx.py build Name.mdx Name.mdd     # writes Name.mdx.koidx, Name.mdd.koidx
    python3 tools/koidx.py check --deep Name.mdx        # the .koidx fits this Name.mdx?

`koidx.py` needs Python 3.8 or later and nothing else, but keep `kosort.py` and
`kosort1_tables.json` next to it. It reads only the header and key section of a
volume, and writes the same index the plugin would build. The MDict files
themselves are not changed, so other readers are not affected.

The plugin uses a `.koidx` only when it fits the volume beside it: its key
count, the length and CRC-32 of the volume's header and key section, and
sampled keys are checked when the dictionary is opened, and the rest of the
file once in the background. A `.koidx` that does not fit (say, left over from
an older export) is ignored and the plugin builds its own index, as without
one. *Index status* shows when a dictionary came with an index, or why its
`.koidx` was not used. The file format is described in `tools/koidx.py` and
`mdict.koplugin/mdict/index.lua`.

Files whose keys are already sorted by the plugin's `kosort-1` order need no
index at all. Exporters can say so with the header attribute
`KOReaderKeyOrder="kosort-1"`; the plugin still verifies the order once in
the background. Such files may lose lookups in readers that binary-search
MdxBuilder's order. `tools/kosort.py` is the reference implementation, with
test vectors in `spec/data/kosort-1.tsv`.

## Layout

- `mdict.koplugin/mdict/`: MDict reader (v1.2/v2, zlib/LZO, encrypted key index),
  the `kosort-1` key order and the sidecar index, lookups, KOReader hooks, and the
  updater (`update.lua`, `updater.lua`).
- `mdict.koplugin/renderers/`: the pager (pager.js/pager.css), the pager document,
  the WebView driver and its backends (Android JNI bridge; a Chromium driven over its
  DevTools pipe, `cdp_bridge.lua`, which is the Kindle's browser in
  `kindle_browser.lua` or a desktop one; the Playwright bridge).
- `mdict.koplugin/widgets/`: the popup widgets (KOReader's HtmlBoxWidget and
  ScrollHtmlWidget interfaces, backed by the pager).
- `kindle/`: the library the Kindle renderer and browser test preload into Amazon's browser (it
  opens the DevTools pipe, keeps the window off the screen and away from the Kindle's
  own software), built into `mdict.koplugin/kindle/kindle_shim.so` by `kindle/build.sh`.
- `android/`: Java side of the Android bridge, built into
  `mdict.koplugin/android/mdict-bridge.dex` and loaded at runtime (no custom
  KOReader build needed).
- `tools/`: test fixture generator, inspection and index tools, the `kosort-1`
  reference implementation, `koidx.py` (prebuilt indexes for dictionary makers), Chromium harnesses, `release.sh`, and `emulator/`
  (an Android emulator shaped like a 7" 300 ppi e-reader, with KOReader; see its README).
- `spec/`: busted specs.

## Development

    busted --lua=luajit spec/         # unit tests
    luacheck mdict.koplugin tools spec
    # popup widgets and menus against a KOReader checkout, rendering with headless Chromium
    # over its DevTools pipe (or MDICT_CHROMIUM_BRIDGE=$PWD/tools/chromium-bridge/bridge.js
    # with NODE_PATH=<dir with playwright>, through Playwright):
    KOREADER_FRONTEND=<koreader>/frontend MDICT_CHROMIUM=<chromium binary> busted --lua=luajit spec/
    kindle/build.sh                   # needs gcc-arm-linux-gnueabihf and libx11-dev
    ANDROID_JAR=.../android-30.jar android/build.sh
    NODE_PATH=... node tools/pager-test/run.js --res <res dir> --out <dir> entry.html
    tools/release.sh [version]        # dist/mdict.koplugin-<version>.zip (version from _meta.lua)

Vertical Japanese test renders need a CJK font with vertical metrics (for
example `fonts-noto-cjk`); without one, Chromium overlaps the glyphs.

## License

AGPL-3.0, like KOReader. See `LICENSE`.
