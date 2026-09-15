# v3.3.1

## What's Changed

- Fix TBR applying Library filter hiding all TBR books

# v3.3.0

## What's Changed

- Add native metadata editor and Hardcover/Google Books/Open Library autofill (Library > Metadata)
- Performance improvements and optimizations based on the benchmarks from Reddit
- Add support for multiple quote files
- Add support for Kindle library (via kindle.koplugin)
- Add book status to Navbar/Book strip controls i.e Reading, Finished, Unread etc
- Add language in Zen Settings > About
- Add context to translations
- Add more toggles/options to Featured widget
- Add first/last name sorting for authors
- Add highlight extend option in 3 dot highlight menu
- Add background hatching to top menu (Controls > Background hatching)
- Add PNG support to Library background
- Add status bar to ZenPM
- Add guided Reader tour/OOBE
- Use stable pages for page stats
- Update Book details (order, items, open tags from book) in Library > Book details
- Updates to Reader top status bar (including colored icons)
- Reserve space in reflowable books (EPUB) for Reader top status bar
- Reset weekly stats on Sunday/Monday (Extras > Stats)
- Move update available button in settings
- Add option to toggle wifi with tailscale
- Fix articles sorting in other languages
- Fix highlight menu overlap
- Fix guided tour bug when Zen mode toggle removed from controls
- Fix final KOSync progress when finishing a book
- Fix dimmed book covers not showing everywhere

# v3.2.2

## What's Changed

- Fix: allow cancelling ZenPM download and time out after one minute
- Fix reader highlight crash
- Fix some icons not rendering

# v3.2.1

## What's Changed

- Fix: deduplicate multiple similar languages i.e en and en-us
- Fix: Variable Book strip control width

# v3.2.0

## What's Changed

- Automatically add and remove ZenPM-installed plugins in Launcher
- Add three-page carousel layout to the page browser
- Add opacity slider to Library background (Library > Background)
- Add new icon for bookmark (dogear) in Reader
- Add font options for TOC and Bookmarks (Reader > Zen page browser)
- Add custom highlight names (Reader > Highlight / Lookup)
- Add folder cover image picker (Hold folder > Edit > Set folder cover)
- Add option to hide the Wi-Fi status icon when Wi-Fi is off (Library > Status bar)
- Add parent + child per folder view in Authors/Series/Tags/Languages tabs
- Add ordering for To Be Read books in Navbar/Home Book Strip widget
- Add more options and ordering to Launcher Book Details
- Add OPDS already downloaded tracking + dim covers
- Allow renaming the To Be Read collection
- Fix restore library location regression
- Fix finished books reporting 0
- Fix brightness schedule not applying after first wake on some devices
- Adjust opening banner border color
- Ignore cbz and Rakuyomi chapters from books finished stat
- Add Hungarian translation
- Bug fixes
