# v1.4.0-beta.6 · 2026-11-16

## What’s new

- **Hide Home pages.** Open **OrbitUI → Home → Layout & modules** to hide a page and bring it back with its configured modules.
- **Hide books from reading history.** Use **Hide from history** in History. Restore books from **Hidden books** in the Recent Books source settings. OrbitUI also excludes those books from its ongoing reading lists.
- **File browser views.** SimpleUI 3.1.0 adds per-tab view and sort options, updated list rows and a flat view that includes books in subfolders. Open **OrbitUI → Dock & interface → File browser appearance** for the file browser’s settings.
- **Bookshelf 6.5.2.** Spine marks such as the favorite icon update after a setting change. Kindle read flags and custom title and author metadata are handled more accurately.

Enable **Include preview releases** under **OrbitUI → System & maintenance → Update OrbitUI**, check for updates, and restart after installing.

Tested with KOReader 2026.07.1 in the Tolino emulator. Physical Bigme and Kindle testing is pending.

# v1.4.0-beta.5 · 2026-11-15

## Text selection shortcuts

- Select text and open **More… → Customize text selection menu**. Tap any of the six positions to choose what goes there.
- Use actions offered by installed plugins, including **Hardcover quote** and KOAssistant quick actions. A KOAssistant shortcut follows the chosen action when the plugin reorders its list.
- **More…** continues to show the full list for the current selection.

To update in KOReader, enable **Include preview releases** under **OrbitUI → System & maintenance → Update OrbitUI**, check for updates and restart after installing.

Tested with KOReader 2026.07.1 in the Tolino emulator, with KOAssistant and a test button that uses the same label mechanism as Hardcover. Physical Bigme testing is pending.

# v1.4.0-beta.4 · 2026-11-15

## What’s new

- **Customize the reading row on Home.** Choose up to five books in **Straight cover row** and show titles or reading percentages under the covers. The default is four books with percentages. **See all** opens the books in progress from your local reading history.
- **Assign shortcuts to dashboard cards.** Use **When tapped** in the card’s settings to pick an action.
- **Literary Clock.** Install the optional add-on from **Get more modules…**, restart KOReader, then add its card from **Shelf modules**. It works offline and uses English quotes.
- **Reader tools.** Hold **Bookmarks** in the reader panel to choose a color for the current page bookmark. Filter the bookmark list by color. When a saved KOAssistant X-Ray is available, the reader panel shows its coverage and can open KOAssistant’s Mentions view.
- **Book information.** The overview shows book language and page count when available.
- **Bookshelf 6.5.1 and SimpleUI fixes.** Arrange Favorites in collection order, see Hardcover ratings rounded to the nearest half star, and use the library in Turkish. SimpleUI keeps goal columns aligned as percentages change and improves compatibility with older KOReader versions.
- **Less background work on Home and in the library.** Statistics updates reuse the cover lists. Android batches cover repaints, and cold library metadata snapshots are written after opening.

Enable **Include preview releases** under **OrbitUI → System & maintenance → Update OrbitUI**, then check for updates and restart after installing.

Tested in KOReader emulators and with the updater from 1.4.0-beta.3 and stable 1.3.0. Physical Bigme testing of this combined build is still pending.

# v1.4.0-beta.3 · 2026-11-15

## What’s new

- **Clearer top-menu footer.** The page number and arrows take priority when the clock and battery crowd the row. To hide device status throughout the top menu, turn off **Dock & interface → Quick controls → Show clock and battery in the top menu** in OrbitUI.
- **Custom text-selection shortcuts.** Choose and reorder up to six actions for the first page of the selection menu. Select **Customize text selection menu** under **More…** while reading, or find it in **OrbitUI → Integrations → Reader panel & X-Ray**. **More…** still gives you the full action list.

To update in KOReader, enable **Include preview releases** under **OrbitUI → System & maintenance → Update OrbitUI**, then check for updates and restart after installing.

# v1.4.0-beta.2 · 2026-11-14

## Bookshelf 6.5.0

- Sort books by **Time left** when KOReader's reading statistics have enough data to estimate it.
- Create collection shelves and arrange their books by hand in **Library (no fixed profile)**. Long-press a book and choose **Add to a shelf**.
- Choose where progress bars and reading bookmarks appear, with separate controls for covers and spine shelves.
- Bookshelf shows which Hardcover connection it uses. It can reuse the Hardcover or ShelfSync plugin, or use its own optional API key. Bulk linking can run in the background, and the existing edition-ID repair option is still available.

## Updating

Enable **Include preview releases** under **OrbitUI → System & maintenance → Update OrbitUI**, then check for updates. Reopen KOReader after installing. The stable channel remains on 1.3.0.
