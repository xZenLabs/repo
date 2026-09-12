# v5.0.1

**Shelves even themselves out.** In Spines view, books share out across the rows on screen rather than filling the first row and stranding the last few.

**Home folders become sections.** Each folder's books stand as a run with the folder's name badged on the shelf edge, like series and author shelves.

Fixes:

- Improvements for extra large DPI layouts
- Extracting page counts no longer runs the device out of memory partway through a large library (#388)
- Scanned page counts survive on libraries of more than about 1200 books
- Leaving a book no longer flashes the file browser before Bookshelf appears, when Bookshelf is not set as the starting screen (#385)
- Covers are no longer left inverted after restarting in night mode, on devices that invert in hardware (most Kindles)
- The folder overlay on folder cards no longer vanishes against a night-mode background

# v5.0.0

**Spines: a third way to see a shelf.** Books stand edge-on on a wooden plank, like a real bookcase. A spine is as wide as the book is long and as tall as its cover's shape, so a shelf reads at a glance. Tap a book and it lifts out of the row. Series and author groups get a badge at the shelf's edge.

- Choose which books turn to face you: favourites, first in series, what you're reading, all, or none.
- Holding the footer's page range now cycles covers > list > spines.
- Pinch to set how many rows a shelf holds. Each shelf remembers its own.

**Page counts.** A new scan fills in page counts for books that don't carry one, so spine widths, `%page_count` and the relative progress bar have something to work from. It runs across a whole shelf and reports what it found.

**Hardcover.** Refresh details for a whole shelf in one go. Enrichment now brings page counts with it.

- The footer reads "9-16 of 247" rather than "Page 2 of 31", in every view.
- Pinching the expanded shelf moves in half steps in list and spine views, so 4 rows can go to 3 instead of jumping to 2.
- Search results can pin to Spines.
- Chips are now called shelves, and the chip bar is the shelf menu.
- Shelf ornaments: drop your own SVGs into KOReader's `icons/bookshelf.ornaments` folder and they'll stand in the gaps on a spine shelf. A couple of plants are seeded there to start you off.

Fixes:

- Titles and authors come from KOReader's custom metadata rather than the filename (#381)
- Calibre columns work when your home folder path ends in a slash (#372)
- OPDS downloads work when KOReader's HTTP proxy is set (#377)
- Series shelves sort by author name (#351)
- An author's card sorts under their own name, not under the first author of their book
- Shelf menu icons stay icons when the UI font is changed
- Page turns no longer flash the footer icons
- Hardcover no longer adds a second author card for a book's translator or editor

# v4.7.0

- Two new colour options: the outline around the selected book, and the shadow behind covers and folder cards (#199)
- New "Tallest cover shape" setting, so unusually tall covers can show more of themselves before being trimmed (#330)
- New tokens: %ssh_icon while KOReader's SSH server is running, and %quote_page and %quote_chapter for the highlight %quote picked (#298, #333)
- %page_num now works in list view lines, not only in the hero
- The book description keeps its text size when the panel is opened by long-pressing a cover (#363)
- Tapping a book in the expanded shelf stays on that book's page instead of jumping back to page 1 (#369)

# v4.6.0

- On-hold and finished books now show their badge and fade on list-view covers, following the same settings as the cover view (#365)
- OPDS downloads use the server's filename when that option is on (#354)
- Pinching to fit more rows fills them again, and redraws faster than before
- The line editor no longer closes when a tap in the Tokens or Icons picker misses a row (#364)
- Swipe to change pages in the token picker

# v4.5.1

- Stack folder tiles no longer show a white corner when the cover drop shadow is off (#362)
- Toggling rotation from a start menu action redraws the shelf straight away, instead of on the next tap
- With a custom chip colour, the currently-reading chip keeps its outline and the divider beside it stays visible
- Calibre custom columns are now read from metadata files up to 64 MB (#357)
- Calibre number columns above a million show in full, rather than as 1.2e+06
- Some English/American spelling inconsistency caught and corrected (#358)
