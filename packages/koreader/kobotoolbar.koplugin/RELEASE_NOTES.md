# v1.0.8 · 2026-10-13

### New: Kobo's reading stats panel
Tap the **ılı** button to open Kobo's stats panel under the top bar, as on a Kobo. The button turns black while the panel is open. Tap ılı again to go back to the normal toolbar, or tap the page to close everything.

- **This chapter:**
  - how much of the chapter you've read, with a progress bar;
  - the time to go.
- **Next chapter:** how long it takes to read. On the last chapter it says "This is the last chapter".
- **This book:**
  - a chart with one bar per chapter (read chapters, the current one and unread ones in different shades);
  - the time left in the book.
  - Tap **< >**, tap the chart or swipe the panel to switch to **Last 7 days**: how many minutes you read this book each day, with your total reading time.
- Times come from KOReader's Reading statistics. When statistics are off, the panel shows pages instead.
- **Long-press ılı** to open KOReader's own Reading statistics.
- A new setting, **"Statistics button opens Kobo's stats panel"**, lets the ılı button open KOReader's statistics instead.

### Changed
- The times in the stats panel are worked out like the ones in the bottom bar since v1.0.7, so they match KOReader's footer and Bookends.

### Install
Unzip and copy the `kobotoolbar.koplugin` folder into `koreader/plugins/`, replacing the old one, then restart KOReader. Your settings are kept.

# v1.0.7 · 2026-10-13

## Kobo reading stats panel

The **ılı** button now opens a reading-stats panel styled after Kobo's own, right under the toolbar.

### New
- **This chapter:** progress bar, % read, and time left in the chapter
- **Next chapter:** time to read it (or "This is the last chapter")
- **This book:** a chart with one bar per chapter, sized by chapter length (chapters you've read are dark, the current one is black, the rest are light grey), plus the time left in the book
- **Last 7 days:** tap **‹ ›** or swipe across the panel to see minutes read per day in this book and your total reading time for it
- Times follow Kobo's style: "14 minutes to go" under an hour, "5.6 hours to go" above
- The ılı button turns black while the panel is open, and the bottom bar hides so you can see the page

### How to use it
- Tap **ılı** again to go back to the normal toolbar. Tapping the page closes everything.
- **Long-press ılı** to open KOReader's full book statistics.
- New setting: **Statistics button opens Kobo's stats panel**. Turn it off to have ılı open KOReader's book statistics, as before.

### Notes
- Times come from KOReader's **Reading statistics** plugin (average time per page). If statistics are off, the panel shows pages instead.
- Books without a table of contents show "No chapters in this book".

### Install
Replace the `kobotoolbar.koplugin` folder in `koreader/plugins/` and restart KOReader.

# v1.0.6 · 2026-10-12

A reading toolbar for KOReader that looks and works like the one on Kobo e-readers. Made to go with **KoboUI**, but it also works on its own.

### Opening it
- **Tap the middle of the page** to show the toolbar. Taps on the left and right still turn pages.
- **Tapping the top** also opens it, instead of KOReader's menu. **Tapping the bottom** does too, and can be switched off.
- **No swipes:** swiping down from the top still opens KOReader's menu, even while the toolbar is open.
- Tap the page again to close it.

### Top bar
- **Its own status bar:**
  - the clock;
  - Kobo's little grey line in the middle;
  - Wi-Fi, only when it's on;
  - KoboUI's battery icon, at the same size as on the Home screen;
  - battery percentage, off by default.
- **← Back to Home / Back to My Books:** goes back to where you opened the book. You can also choose to always go to Home or always to My Books. Without KoboUI it says "Back to Library" and goes to KOReader's file browser.
- **Buttons:**

  | Button | Opens |
  |---|---|
  | ☼ | KoboUI's light panel, under the button; KOReader's frontlight dialog without KoboUI |
  | Aa | KOReader's font and layout panel |
  | ılı | reading statistics for this book |
  | ⚙ | KOReader's menu |
  | ••• | a drop-down of actions you choose |

- **Customisable:** hide or reorder any button. You can also add your own buttons, each with a name, an icon (70 line icons) and any KOReader action.

### Bottom bar
- **PAGE 336 OF 1006.** Tap it to switch to pages left in the chapter, time left in the chapter, time left in the book, or percent read.
- **Progress slider** with Kobo's double-ring knob, and |< >| to jump to the previous or next chapter.
- **RETURN TO PAGE N** appears after you skim, with a mark on the slider where you were.
- **Chapter name:** tap it for the table of contents. Next to it are the notes/bookmarks and search buttons.

### Look
- Sizes are matched to Kobo's own toolbar on a Kobo Clara Colour (1072×1448).
- **Fonts:**
  - The text uses the **Label Font chosen in KoboUI** (Settings → Style → Label Font). Without KoboUI it uses KOReader's UI font.
  - "Back to …" and the chapter name are bold, even with fonts that have no bold file (such as a single-file Jost).

### Settings
Gear tab → **Kobo-style toolbar**, also in ••• → Toolbar Settings:
- where taps open it (middle, top, bottom) and how wide the middle area is;
- where "Back to" goes;
- the toolbar buttons and the ••• menu;
- battery percentage and the Wi-Fi icon;
- what the page line shows, and chapter marks on the slider.

### Install
Unzip and copy the `kobotoolbar.koplugin` folder into `koreader/plugins/`, then restart KOReader.

Tested with KOReader v2026.07.1 and KoboUI v1.1.24.
