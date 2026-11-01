# v1.13.0 · 2026-11-01

## modern_menu 1.13.0

A swipe steps back through the menu, the breadcrumbs can sit at the bottom, and the book's own navigation screens open on their own.

### Changes
- A right-to-left swipe returns to the parent menu. On the top menu, the same swipe closes it. This still works when the list is long enough to scroll
- **Breadcrumbs at the bottom** in Modern Menu settings moves the trail under the list. On a full-screen menu that row keeps its own space at the bottom
- Table of contents, Bookmarks, Book map, Page browser, Go to page, and Skim document close the menu, so KOReader's own screens are what you use to move through the book

### Install
1. Download **modern_menu.koplugin-v1.13.0.zip**
2. Extract into your KOReader `plugins/` directory
3. Restart KOReader and enable **Modern Menu**
4. Install Kobold, Simple UI, Quick Menu, Neo Quick Settings, or Shortcuts Toolbar as well if you use those

# v1.12.0 · 2026-10-30

## modern_menu 1.12.0

Menu search opens again, toggles stay intact while a long list scrolls, and the Files tab is back when Kobold is installed.

### Changes
- **Menu search** under Home → Help opens the text box. A result can be opened, or the menu can walk to that entry
- In a long list such as User plugins, the switch thumb stays inside the track while you scroll. The scrollbar responds as soon as the list is open
- With Kobold installed, the **Files** tab is in the menu again. It closes Kobold and, from a book, leaves the book on the file list

### Install
1. Download **modern_menu.koplugin-v1.12.0.zip**
2. Extract into your KOReader `plugins/` directory
3. Restart KOReader and enable **Modern Menu**
4. Install Kobold, Simple UI, Quick Menu, Neo Quick Settings, or Shortcuts Toolbar as well if you use those

# v1.11.0 · 2026-10-26

## modern_menu 1.11.0

The menu refreshes a smaller part of the screen, so an e-ink update finishes sooner.

### Changes
- Opening the menu, switching tabs, moving through a submenu, and dragging a Quick Menu slider refresh the menu sheet. The page below a short menu stays as it is
- When the sheet grows or shrinks, the refresh covers the old and new height, so the page that was covered or uncovered is drawn
- A check, radio, or changed label refreshes those rows as one block
- A long list paints the rows on screen first. The rows just above and below are built after that paint, and the rows on screen stay where they are

### Install
1. Download **modern_menu.koplugin-v1.11.0.zip**
2. Extract into your KOReader `plugins/` directory
3. Restart KOReader and enable **Modern Menu**
4. Install Kobold, Simple UI, Quick Menu, Neo Quick Settings, or Shortcuts Toolbar as well if you use those

# v1.10.0 · 2026-10-25

## modern_menu 1.10.0

The menu is faster on e-ink. Taps and long lists do less work, and the screen refreshes only the part that changed.

### Changes
- A tap updates the row that changed, and leaves the tabs, status bar, and shortcut row alone
- Long lists build the visible rows and a short buffer, instead of every row at once
- Fit-to-content and percentage heights refresh the menu sheet when its size stays the same, instead of the whole screen
- Quick Menu toggles, slider drags, and scrolling each paint once per gesture

### Install
1. Download **modern_menu.koplugin-v1.10.0.zip**
2. Extract into your KOReader `plugins/` directory
3. Restart KOReader and enable **Modern Menu**
4. Install Kobold, Simple UI, Quick Menu, Neo Quick Settings, or Shortcuts Toolbar as well if you use those

# v1.9.0 · 2026-10-20

## modern_menu 1.9.0

The status bar can be hidden, and the battery can show as a percentage.

### Changes
- **Hide status bar** removes the clock, contrast, Wi-Fi, and battery row from the menu. The close mark moves to the title row
- **Battery as percentage** shows the charge as a number instead of the battery icon, in the menu and in the file browser

### Install
1. Download **modern_menu.koplugin-v1.9.0.zip**
2. Extract into your KOReader `plugins/` directory
3. Restart KOReader and enable **Modern Menu**
4. Install Kobold, Simple UI, Quick Menu, Neo Quick Settings, or Shortcuts Toolbar as well if you use those
