# v5.0.6

Fixes blurred cover images on the hero card, and books in a series sorting to the end of most-recently-added shelves

# v5.0.5

Fixes a crash when opening a second book, and stops KOReader deleting Bookshelf's cached data

# v5.0.4

Dropshadow colour fix for dark mode, and dark mode toggle performance improvements

# v5.0.3

Patch for v5.0.2.

New:

- Chinese, Japanese and Korean titles now stand upright on spines instead of rotated on their side, thanks to @ksaMask123 (#393)

Fixes:

- Folder tiles keep their card colour in night mode, so the folder name is readable again (#395)
- In Spines view, the status and favourite marks no longer crowd out the title on thicker spines

# v5.0.2

Patch for v5.0.1.

Fixes:

- Paging a large genre or author shelf in Spines view now reaches every book, forwards and backwards, instead of jumping to the next group after the first page
- The Covers shelf style no longer offers List columns and List rows, which only apply to the list
- Books downloaded from an OPDS catalogue are named the way KOReader's own browser names them, so a book already downloaded is recognised instead of fetched again (#389)
