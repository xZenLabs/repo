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

# v4.5.0

**Kindle library**

- On a Kindle, your own Kindle books can now be a shelf alongside the ones you side-load: long-press any chip, **+ Add new chip**, then pick **Kindle Virtual Library**
- It needs [kindle.koplugin](https://github.com/kaikozlov/kindle.koplugin) installed, and only appears where it is. That plugin does all the work of reading and converting your Kindle library; Bookshelf just shows you what it finds, so anything about the conversion itself belongs on its issue tracker rather than this one
- Sorted, filtered and searched like any other shelf, with their own cover art, and they count towards Shelf size
- Titles the Kindle took from a filename are tidied up: an author's name is removed only where the catalogue credits that name, so an unrecognised subtitle or translator is left alone
- The first time you open a Kindle book, kindle.koplugin has to convert it. That takes a few minutes and cannot be interrupted, so Bookshelf asks first, and only once per book
- A new Kindle chip filters out the formats KOReader cannot open, so the shelf is not padded with books that can only refuse. Older MOBI and AZW purchases and `.azw3` files are the usual ones. Show them from the chip's **Filters** if you would rather see everything: tapping one then says why it cannot be opened, instead of dropping you into the file browser
- Move, Delete and Reset are left out for these books, since the files belong to your Kindle's library rather than to you
- Searching your library includes your Kindle books, and searching from an OPDS catalogue now offers **Search my library** alongside the catalogue's own search

**Chips**

- Creating a chip opens the source picker straight away: the source is what the chip is for, and what gives it its name

**Covers and list lines**

- Two new options under Settings > Cover display: **Square cover corners** and **No cover drop shadow**, for a flatter, crisper grid. They work independently, so you can square the corners and keep the shadow, or the other way round. Dropping the shadow gives its reserved pixels back to the cover, so covers grow slightly (#353)
- New `%genres` and `%genre` tokens for list lines and hero text: every genre comma-separated, or just the first where there is no room for more. These are what calibre calls tags, and `[if:genres]...[/if]` gates them like any other token (#346)
- `%sysused` uses a short "M" suffix, matching `%ram`

**Faster**

- The shelf opens faster, and the bigger your library the more it saves. On a Paperwhite 5 with around 250 books, the default shelf went from 2.4 seconds to 0.9, and a grouped Series shelf from 2.3 to 1.4
- Covers stay ready between launches instead of being rebuilt every time the shelf opens. The first launch after updating still has to build that cache, so the speed-up starts from the second one
- Shelf page turns are quicker, and the page-turn animation now defaults to Fast. Medium, Slow and Off are all still there, under Advanced settings > Page turn animation, if Fast still feels slow on your device
- The start menu opens and closes faster
- The book details popup opens quicker, and pinching to change how many covers fit settles in one pass rather than two

**Fixes**

- Two small micro-modules share a hero row instead of each taking a full one (#359)
- Filters set on a Kobo shelf are applied
- Kobo shelves sort by progress and by last opened correctly
- Reopening Bookshelf puts you back inside a Format or Rating group you had drilled into, rather than at the top of the chip
