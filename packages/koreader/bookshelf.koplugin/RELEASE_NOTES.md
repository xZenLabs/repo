# v5.0.8

Sorting by Title now ignores a leading "The", "A" or "An", and uses Calibre's Title Sort where a book has one (#401). Shelves sorted by title will reorder on upgrade.

Fixes:

- On a Series shelf that also shows standalones, books not in a series no longer sort to the end (#400)
- Covers are no longer grainy on Kobo and Onyx greyscale devices
- Ornament SVGs are no longer ignored when their viewBox uses commas, or when they have none at all
- A series named Calibre-style ("Dark Tower, The") now reads the right way round on its card

# v5.0.7

Books sideloaded after you have opened a book now appear on the shelf on their own, instead of needing a swipe-down refresh

# v5.0.6

Fixes blurred cover images on the hero card, and books in a series sorting to the end of most-recently-added shelves

# v5.0.5

Fixes a crash when opening a second book, and stops KOReader deleting Bookshelf's cached data

# v5.0.4

Dropshadow colour fix for dark mode, and dark mode toggle performance improvements
