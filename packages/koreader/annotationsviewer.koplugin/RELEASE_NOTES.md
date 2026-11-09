# v0.5.1 · 2026-11-09

## New
- Sort in up to three steps (sort by, then by, then by), for example author, then book, then place in the book. Last opened book is a new sort key
- All annotations and a single book keep their own sort. A single book starts in reading order
- In a single book you can sort by date, position or chapter, for example chapter, then newest first
- Date can be followed by book and position, for example newest day first, then book, then position

## Changed
- The sort order dropdown has chips and a direction bar, on smaller screens this is more simplified
- Sorting by author keeps each book together and ignores capitals
- The line under the book title in a single book is larger

Install: unzip into a folder named `annotationsviewer.koplugin` in KOReader's `plugins` folder and restart.

<img width="342" height="636" alt="image" src="https://github.com/user-attachments/assets/58a4fbc8-1967-4002-84d5-120d9c7f99f3" />

# v0.5 · 2026-11-08

This is a big update, it changes the overall look of the plugin.

## New
- Chapter headings in the list, they look like the book title
- Saved filters, one tap to bring a filter back
- Search matches are underlined in highlights and notes
- Landscape width setting
- Page number in the annotation sheet
- Chinese, Japanese and Korean text wraps correctly (thanks gytwo, pull request #8)
- Lines per note setting, long notes end with "..." and tap shows all of it
- Menus, dropdowns and dialogs pass gestures you don't use on to KOReader
- Line spacing setting, also negative to bring lines closer together
- Own font and size for notes, plus space above the note and an extra indent for it
- Own font and size for the author name, and capitals or as written for book and chapter titles, the chapter · date line and the author
- Scrollbar marks follow the sort order: books, authors, months or chapters (also in one book)

## Changed
- Sort order is a dropdown now
- Books, Chapters and Tags pickers all work the same, with an Only these / Hide these switch
- Settings are split into Text and Spacing, with a preview on top. Spacing is grouped by where the space is: page, between annotations, book heading, highlight text and your note
- Menus use Prev / Next buttons like the list instead of a scrollbar. Swipes and page keys work too
- Default content text size is 16
- Night mode keeps the real highlight colors
- Text keeps clear of the scrollbar when the horizontal margin is small

Install: copy the `annotationsviewer.koplugin` folder from the zip to KOReader's `plugins` folder and restart.

# v0.4 · 2026-05-05

## New Features
* **Annotations viewable from within book** – A new menu entry for current-book annotations makes it easier to access and manage your notes from within a book.
* **Enhanced Filtering** – Extensive filtering options help you find the notes you need quicker and more easily. Following options have been added:
   * Filter by Chapter (only if annotations from a single book are visible)
   * Exclude Color/Style.
   * Filter and exclude by highlight text.
   * Filter and exclude by note text.
   * Show/Hide annotations with notes.
* **Hide repeat headers** – New settings allow you to enable or disable title and info header for subsequent annotations with customisable matching based on specific fields for a cleaner experience.
* **Pagination Style Options** – Enjoy a more customized experience with new pagination styles. Currently, these consist of:
   * Default style (matching KOReader pagination)
   * Left/right aligned (matching Project Title pagination)
   * Vertical scrollbar (with and without previous/next page buttons).

## Improvements
* **Clear/Apply Filters Button** – A new button lets you quickly apply filters. This can be disabled from the settings for a cleaner look.
* **Gesture Support** – Improved gesture handling so that gestures set up in the file manager or reader still work when plugin is open. Settings for swipe gestures has been added as well.
* **Annotation Caching** – Annotations are now cached, which helps with loading speed of large amount of annotations.
* **Annotation Gathering** – Now also uses KOReader's cached book information DB for gathering annotation which should cover most use cases.
* **Menu** – Adjusted menus so they are a bit more organised.

# v0.3 · 2026-02-03

## What's Changed
* Author name now shows up in annotation info and details
* Sorting options have been added
* Added support to go through pages with vertical swipes
* Now shows all active filters in subtitle
* Added support for custom metadata
* Now gets highlight colors dynamically, so you can use this now in combination with patches that modify these colors :)
* General fixes with tap behaviour in footer and content height generation
* feature: fire `AnnotationsModified` events when annotations are modified by @SethMilliken in https://github.com/xblain/annotationsviewer.koplugin/pull/1

## New Contributors
* @SethMilliken made their first contribution in https://github.com/xblain/annotationsviewer.koplugin/pull/1

**Full Changelog**: https://github.com/xblain/annotationsviewer.koplugin/compare/v0.2...v0.3

# v0.2 · 2026-01-31

**Full Changelog**: https://github.com/xblain/annotationsviewer.koplugin/compare/v0.1...v0.2
