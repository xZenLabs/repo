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

# v1.4.0-beta.1 · 2026-11-14

## OrbitUI settings and Bookshelf patches

- **Custom quick actions** opens the saved list and its create button from **Dock & interface**.
- Pick the app-bar icon at **Dock & interface → Icons, fonts & shared appearance → Icons → System Icons → Tab Bar → Tab: OrbitUI**. With the picker set to **Default**, you can supply `koreader/icons/orbitui_menu.svg`.
- OrbitUI runs KOReader’s registered Bookshelf patch hooks. **Progress Bookmarks** settings appear under **Library → Advanced library settings**. **Bookshelf Bar Styles** appear in the line editor for a line containing `%bar`.
- The OrbitUI tab offers **Restart KOReader** on supported devices. Android shows **Close KOReader** and prompts you to reopen the app.

## Reader and library

- Comic archive metadata from ComicInfo now feeds Library and book information. KOReader custom fields retain priority.
- Library searches reuse normalized book text between queries.
- The reader has a compact text-selection menu, dictionary highlight feedback, native footer controls, and optional Syncery and Bluetooth HID shortcuts when available.

## Updating

Enable **Include preview releases** under **OrbitUI → System & maintenance → Update OrbitUI** and check for updates. Reopen KOReader after installation. Stable remains on 1.3.0.

# v1.3.0-beta.1 · 2026-11-13

## One place for OrbitUI settings

- The OrbitUI grid tab sits directly beside Quick Actions in KOReader’s top menu. It replaces the separate Bookshelf settings tab and opens the shared settings from Home or from a book.
- **Home** groups the dashboard, cards and wallpaper. **Library** groups shelves, covers and themes. **Dock & interface** covers shortcuts and shared appearance. You can search across the settings.
- Long-press a dock shortcut to add, replace or remove it. **Edit dock** also lets you reorder shortcuts. Open a library profile, folder, collection or quick action right from the dock.
- Fresh setups start with **Home, Library, History and Power**. Existing docks retain their shortcuts. Manga remains available as a shortcut, and existing manga shortcuts can still open their library start menu.

## Updating

Open the OrbitUI updater, enable **Include preview releases**, and check for updates. Restart KOReader after installing. In this beta, the updater is under **OrbitUI → System & maintenance → Updates**.

The menu and dock were tested on a Bigme B7 Pro. The default dock order was tested on an emulated Kobo. The stable channel continues to offer 1.2.0.
