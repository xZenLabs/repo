# v1.5.0 · 2026-11-11

## Styles to download

Tools > Reading Log > Styles and colours > **Get more styles…** lists the styles in [reading-log-styles](https://github.com/stevenzamora1/reading-log-styles). Tap one to download it, and again later to update or remove it.

Seven so far: **Christmas**, **Gothic**, **Forest**, **Ocean**, **Space**, **Honey** and **Winter**. Each one redraws the rings, the days of the week, the goals, the progress bars, the Monthly challenge, the calendar, the book covers and the Dashboard's tabs, and brings its own colours.

- **Colours**: any style can go on White, Dark or Paper instead of its own colours (Styles and colours > Colours).
- **Behind the Dashboard's cards**: keep the style's page colour, or your home screen's own background.
- **Your styles…** works without Wi-Fi. Hide Cute, Cyber or Dark Academia from the Style list, or delete downloaded styles.

## ZenOS

Every card, the Mini dashboard and the Dashboard are widgets for [ZenOS](https://github.com/xZenLabs/zen-os)'s Home (Zen Settings > Home > Widgets). Long-press one for its settings, text size and height. Swipe the Dashboard to turn its page.

**To have the Dashboard alone on Home:**

1. In Zen Settings > Home > Widgets, turn off every widget except Zen's Reading stats.
2. Turn on Reading Log · Dashboard.
3. Turn off Reading stats.
4. Optionally, long-press the Dashboard > Height on Home > 10/10.

Zen won't let you turn off its last widget, so the Dashboard has to go on before Reading stats goes off.

## The Dashboard full screen

Tools > Reading Log > **Open the dashboard**, or the new **Reading Log dashboard** gesture, shows the Dashboard on a screen of its own, with or without a home screen plugin.

- Swipe left or right to turn the page.
- Swipe down, or tap the X, to close it.
- Long-press a card for its settings.

## New cards

- **Pages goal**: pages read this year, this month or this week against a goal you set, how far ahead or behind you are, and how many pages a day it takes.
- **Finish speed**: a dot for every book you finished, from a day to a year, with how long a typical book takes you, and your fastest and slowest.
- **Decades**: when the books in your library were published, with the typical year, your oldest and your newest. With Bookshelf 6.4 or newer it uses the dates you set there.

## Mini dashboard

- **Up to four cards**, and they can **stack**: the first on the left and the others on top of each other on the right (This week over the Monthly challenge, say).
- "With three cards or more" sets Auto, Side by side or Stacked on the right.
- Continue reading and Reading and today's rings now grow with a taller Mini dashboard ([#9](https://github.com/stevenzamora1/reading-log/issues/9)).

## Your reading

- **The Yearly page goes back through the years** ([#6](https://github.com/stevenzamora1/reading-log/issues/6)). Its arrows step back up to ten years, like the Monthly page's months.
- **What counts as finished is up to you** ([#7](https://github.com/stevenzamora1/reading-log/issues/7)): Marked finished, Read to the end (from the reading statistics), or Either.
- **Change a book's dates**: set when you started or finished a book when the statistics have it wrong. Every card uses them.
- **Goals for one collection**: Year goal and Pages goal can count only one collection's books, so a TBR collection becomes "read all of these this year".
- **Quotes can open at the highlight** instead of where you left off.
- **When tapped can run any KOReader action** on ZenOS, Simple UI and full screen, from the same list as gestures.

## Easier to use

- **Simpler menus.** Tools > Reading Log has five items:
  - Open the dashboard
  - Styles and colours
  - Your reading
  - Reader panel
  - About and updates
- **The long-press menu on the Dashboard has four:**
  - Dashboard pages
  - Styles and colours
  - Card settings
  - Reset to default
- **Lifetime pages** shows a bigger total. Its year, month and week rows can each be hidden.
- **Thicker progress bars** on Continue reading and Book club.

## Bug fixes

- Switching from Dark Academia or Cyber to another style kept the old page, tabs and headings. A style's colours now always go when you leave it.
- "On pace" on the Monthly challenge was white on white on dark cards (Dark, Cyber).
- Bookshelf's log showed "micro-module failed to load … unexpected symbol" for `._alm_*.lua` files a Mac left behind. Reading Log now removes them.
- Continue reading didn't grow on a taller Mini dashboard; only the cover did ([#9](https://github.com/stevenzamora1/reading-log/issues/9)).

## Languages

**Ukrainian**, by [@advokatb](https://github.com/advokatb). Thank you!

## Updating

Tools > Reading Log > About and updates > **Check for updates**, then restart KOReader. Or download `readinglog-1.5.0.zip` below and replace the `readinglog.koplugin` folder in `koreader/plugins`.

The full list is in the [changelog](CHANGELOG.md).

# v1.4.0 · 2026-10-30

Reading Log is now one KOReader plugin that works with Simple UI and with Bookshelf. New in this version: Cyber and Dark Academia styles, five ornaments, a Device card, a Lifetime pages card, and a small panel under the reader's menu.

**To install:** download `readinglog-1.4.0.zip` below, unzip it, copy the `readinglog.koplugin` folder into KOReader's `plugins` folder and restart KOReader. You can also install it from the App Store plugin. On the Simple UI version already? Use Tools > Reading Log > Check for updates.

## Coming from 1.3

- **Bookshelf micro-modules version:** install the plugin as above. On the next start, Reading Log copies your settings across and offers to remove the old copy in `settings/bookshelf/micromodules`, then asks you to restart. Your Bookshelf layouts keep their cards.
- **Simple UI version: replace the `readinglog.koplugin` folder. 

Your settings live in `koreader/settings/readinglog.lua`, so updates keep them.

## New

- **One plugin for Simple UI and Bookshelf.** It installs and updates like any other KOReader plugin, with no files to copy into Bookshelf's settings. Bookshelf 6 loads the cards straight from the plugin. Both home screens share one settings file.
- **Check for updates** in Tools > Reading Log, now for Bookshelf too. It shows what's new and installs only when you say so. It can also check once a day on its own.
- **Style: Cyber.** A black page in neon yellow and cyan, cards with two corners cut off, and every card's cyber look at once. Rings become segments that light up, Continue reading becomes a HUD, the Year goal a terminal, the Monthly challenge a neural network, the quote cards a terminal window, Reading trends a diagnostics readout and the Finish forecast a countdown. The clock and page titles glitch.
- **Style: Dark Academia.** Parchment cards on a dark study's page, set in a serif with a brass rule inside each frame. Rings become pocket watches, Continue reading hangs your cover in a gilt frame, the Year goal is a globe you shade in as you read, and the Monthly challenge is a chess board that plays the Immortal Game move by move. Bar charts are rows of candles, the quote cards manuscript pages with a wax seal, and the Finish forecast an almanac entry.
- **Modules as ornaments:** five new modules with no card. They hang on the wallpaper or stand on Bookshelf's shelf among your books:
  - **Books this year:** how many books you've finished this year.
  - **Streak flame:** your reading streak, as a flame that grows the longer it runs.
  - **Letter board:** a few words of your own.
  - **Today's pages:** the pages you've read today.
  - **Pages turned:** every page you've turned, or just this year's.
- **Device card:** battery, storage, memory, Wi-Fi and front light, each with a level bar. Tap it for KOReader's battery statistics.
- **Lifetime pages card:** every page you've ever turned in KOReader, your daily average, a bar to the next round number, and this year's, this month's and this week's pages.
- **Reader panel:** off until you switch it on in Tools > Reading Log. The reader's top menu opens on a small panel with the cover, two lines of figures, a progress bar (or this week's rings) and up to eight buttons. Each button can run any action from KOReader's gesture list, with a glyph, one of KOReader's icons or a picture of your own. Every part can be switched off.

## Changes and fixes

- **Library stats match Bookshelf's count.** With Bookshelf, each book counts under the status Bookshelf gives it, like its own Shelf size card. A book marked New no longer counts as Reading because of a percentage left in it.
- **Simple UI: no white box around framed cards.** Cyber and Dark Academia cards and the ornaments now sit straight on the wallpaper.
- **Quote of the day:** Another picks a random highlight now instead of the next one in the same book.
- **Bookshelf:** cards show the colours you give them with the palette icon (#4). Opening a book and its book menu use Bookshelf's own calls (#5). Times follow KOReader's 12- or 24-hour clock.


## What you need

KOReader with Simple UI 2.7.5 or newer, or Bookshelf 6.0 or newer

# v1.3.0 · 2026-10-24

## Reading Log 1.3.0

A Cute style, a cover calendar, more quote cards, and a faster Dashboard.

### New cards
- **Cover calendar**: every day of the month with the cover of the book you read most that day, the time read under it, and the month's pages, books and time along the top. Tap a day for its books; **Today** jumps back to this month. It has its own Dashboard tab, **Calendar**.
- **Week in covers**: this week's covers in one row, as a card or a small card in the Mini dashboard.
- **Quote of the day 2, 3 and 4**: each shows a random highlight of its own, never the same one as your other quote cards.

### Style: Default or Cute
Dashboard settings (or Look and colours on any card) > **Style** > **Cute** turns on every cute look at once:
- **Hearts instead of rings**: the outer heart fills with pages, the inner one with time, and a missed day gets a broken heart.
- **Monthly challenge**: a peony that colours in as you near your goal.
- **Book club**: a garden, with vine progress bars and a dragonfly on finished covers.
- **Year goal**: a jar of hearts that spills over once you pass your goal.
- **Quote cards**: on notebook paper.
- **Cover calendars**: as tilted polaroids.
- **Continue reading**: a scrapbook.
- **Reading trends**: on sticky notes.
- **Charts**: book spines and hearts.
- **Today's timeline**: a sky from sunrise to night.
- **Finish forecast**: a desk calendar.

### Also
- Control centre buttons can show a PNG or JPEG of your own
- **Faster**: cards that haven't changed are copied instead of redrawn
- Room for 8 Dashboard tabs.

**Install:** unzip, then copy everything inside `micromodules` into `.adds/koreader/settings/bookshelf/micromodules/` and restart KOReader. Your settings are kept.

# v1.2.0 · 2026-10-22

Reading Log 1.2.0: now in four languages

Reading Log now shows in the same language as KOReader: English, Italian, Spanish or Brazilian Portuguese. 

Thanks to [@DevGizmo86](https://github.com/DevGizmo86), who built the translation system and the Italian translation. 

Also in this release

Tab names and the Random pick heading shrink a little instead of being cut off when a translation is longer.
KOReader’s log notes which language Reading Log loaded, which helps if it ever stays in English.

To update, download reading-log-1.2.0.zip and copy everything inside its micromodules folder into koreader/settings/bookshelf/micromodules/, replacing the old files.

# v1.1.0 · 2026-10-20

### New in 1.1

- **Dashboard**: Trends and Library pages, up to 7 tabs, move tabs, remove pages you added, reset the whole Dashboard.
- **Mini dashboard**: one row of up to three small modules for the top of the home screen.
- **Reading trends**: your last 90 days against your year (time, pages, reading days, session length, speed, books finished).
- **Monthly challenge**: one goal for the month, picked from your last three months or set by you.
- **Finish forecast**: when you'll finish the books you're reading at your recent pace, and where your year is heading.
- **This week vs last**: your average a day this week against last week (or month, or year).
- **Today's timeline**: each sitting today on a line through the day.
- **Control centre**: up to 8 buttons for any action, with brightness and warmth.
- **Library stats**, **Most-read authors**, **Random pick** (only the next book of a series) and **Quote of the day** (from your own highlights).
