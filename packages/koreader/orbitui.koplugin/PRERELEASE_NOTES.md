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

# v1.2.0-beta.4 · 2026-11-11

## Home

- The straight cover row has clearer card borders, an aligned greeting and date, larger add and search icons, and a stronger divider below the book progress labels.
- Want to read and Recently added each have their own card and pager. Their cover stacks are larger, with more room for the covers above each label and arrow.
- The reading streak and Monday–Sunday reading chart sit beside the reading goal. They use KOReader's local statistics and are available in English and Swedish.
- The Silverfish companion and its details make better use of the space beside the current book.

## SimpleUI 3.0.3 integration

- Copy visibility settings for shared File Manager and Reader menu items.
- See a folder's name on its File Manager placeholder when no cover is available.
- Tiny Critter has updated bubble tails and shadows.

## Testing

The Home layout and both shelf pagers were checked on a Bigme. One Recently added cover briefly used a placeholder after paging and returned after restarting KOReader. The combined release was checked with local tests and upgrade checks.

Choose the **preview** channel in OrbitUI's updater to install this beta. The **stable** channel offers 1.1.0.
