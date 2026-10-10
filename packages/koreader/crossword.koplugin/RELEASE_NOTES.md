# v0.4.0 · 2026-10-10

## v0.4.0

### NYT Archive fixes
- **Correct coverage.** The `doshea/nyt_crosswords` archive stopped updating in March 2018. The source is now labelled **New York Times (Archive 1976-2018)**, and the README no longer claims "1977 to present".
- **Clear messages instead of HTTP 404.** Dates outside 1976-01-01 – 2018-03-09, or on a day missing from the archive, are refused before downloading, with a message saying why.
- **Exact gap list.** The plugin now knows all ~100 missing stretches (from the repo's full file list), not just the two named in its README. 2016-03-01, which the old check wrongly blocked, works again.
- **Date prompt** shows the available range and the main gaps. The relative-date buttons (Yesterday / 3 days ago / 1 week ago) and the "Today's" entry are hidden for this source, since those dates never exist in the archive.

### New
- **Previous / next puzzle.** While an NYT archive puzzle is open, **☰ Menu** shows `◀ date` / `date ▶` buttons that open the neighbouring day's puzzle, skipping missing days. Progress on the current puzzle is saved, and if the download fails you stay where you are.
- **Offline NYT archive.** Copy the repo (`nyt_crosswords` or `nyt_crosswords-master`) into `koreader/data/crossword/` or the plugin's `puzzles/` folder. *By date…* and the previous/next buttons read puzzles from there and only go online for dates they can't find.
- **NYT `.json` files in the library.** Loose archive `.json` files in either folder appear in the library alongside `.puz` and `.ipuz`.
- **New puzzle folder: `koreader/data/crossword/`.** Scanned in addition to the plugin's `puzzles/` folder. It survives plugin reinstalls, so it's the recommended place for your files.

# v0.3.0 · 2026-06-12

- Clue banner is now tappable: tapping it pops up the full, untruncated
  clue so long clues that get cut off in the banner are still readable.
- Always show the clue for the word under the cursor, regardless of which
  cell within the word is focused (previously the banner blanked out on
  any cell that wasn't the word's first cell).
- Add a directional pad to the right of the keyboard for cell-by-cell
  navigation, handy when most cells are already filled. 
- The keyboard now  expands to fill the remaining width (shrink_unneeded_width off) instead
  of sitting shrunk-and-centered with empty side margins.

# v0.2.1 · 2026-06-07

- fix: clu banner not shown
- only show clue banner on a word's starting cell

# v0.2.0 · 2026-05-25

- Add dispatcher action and refactor menu system to support both traditional and quick dialog menus

# v0.1.0 · 2026-05-19

- initial release
