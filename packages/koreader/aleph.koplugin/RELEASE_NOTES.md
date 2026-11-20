# v1.3.0 · 2026-11-20

## Aleph 1.3.0

**Goodreads is built in, fourteen new widgets, a richer X-Ray, Collections from Calibre, French and Italian, and a lighter Aleph on low-memory devices.**

Download **aleph.koplugin.zip** below and follow the [Updating guide](https://github.com/lara-2-ko/aleph.koplugin/wiki/Updating): delete the old `aleph.koplugin` folder, copy the new one in its place, restart KOReader. Your settings, Home layouts, pins and library are kept.

### Goodreads, built in
- Aleph keeps Goodreads up to date itself: **Currently reading** when you start a book, your **progress**, **Read** with the day you finished and your stars, and status changes from a book's page, Home or KOReader. All in the background, so reading never waits.
- **A book is never marked Read twice.** Aleph asks Goodreads first every time.
- **Offline?** Changes wait and are sent later. **Waiting to send** shows them.
- **You no longer need the Goodreads plugin by advokatb.** If it is still on, Aleph offers to turn it off. Your sign-in, settings and book links carry over.
- The sign-in row now says **Signed in** or **Not signed in**.

### New widgets
- **Goals** (with rings on a large tile), **Daily goal**, **Weekly goal**, **Monthly goal**
- **Reading DNA**, **Monthly challenge**, **Reading rhythm**, **Year projection**, **Diversity score** (after BookOrbit's)
- **Reading bingo**: a card of 12 or 24 reading challenges, filled as you finish books
- **Weather**, from Open-Meteo, only when Wi-Fi is already on
- **Hours read**: all your hours read, since when, this year and how many books
- **Time read**: this year's hours month by month, and **Books and pages**: books finished and pages read each month (after the Reading Log plugin's charts)
- Every widget in its own colour on colour screens, and **you can choose any widget's colour**: Customize Home → select it → **Colour** (eleven colours, or its own)

### X-Ray
- A name's card shows **where it comes up** (chapter by chapter, first seen, most mentions, latest) and **who it is often with**.
- **Detailed descriptions** (optional, with AI): main characters in three or four sentences.

### Library
- **Collections from Calibre:** a `#collections` column in Calibre puts your books in KOReader collections.
- **Rename and delete collections:** hold one in the collection list.
- **Sort Reading by progress**, most or least read first.
- **Tap an author** on a book's page to see their books.

### Home and reading
- **Font for Home** and its own **font and size for the top menu**.
- **Home's text stays readable over any wallpaper:** Auto, Dark or Light, with an Outline option. The picture picker opens in your e-reader's `images` folder.
- **A way back after any jump:** after the contents, Go to page, a link, a bookmark or a pin, "Go to most recent page" takes you back.
- **Finish forecast** uses a new book's real pace.
- **Hold Wi-Fi** in the top menu for the networks in range; the **Bluetooth switch** works with the Kobo plugin.
- Aleph's pages follow the screen when it turns.
- **Goal pace** says both what is left and how far you are from pace ("10 to go · 8 behind pace"). **Rename a Home page** from Customize Home → Pages, and empty pages are skipped. Customize Home's bar fits at large interface sizes. (#5, thanks @N9TailedFOX)

### Languages
- **French** and **Italian**. Portuguese and Spanish checked and corrected.

### Lighter and steadier
- Background work (weather, collections, Goodreads, covers) waits when memory is low, and Home frees memory when it runs low.
- A timer that piled up while reading is fixed.
- A tap on a text field always brings the keyboard up.
- `crash.log` now records memory use and background jobs, to help with any report.

Full list of changes: [MODIFICATIONS.md](https://github.com/lara-2-ko/aleph.koplugin/blob/main/MODIFICATIONS.md). Screenshots: [wiki](https://github.com/lara-2-ko/aleph.koplugin/wiki/Screenshots).

**Also attached:** `aleph-wallpapers.zip` (seven seasonal wallpapers, now at the Kindle Colorsoft's size, with Three Kings and St Patrick's Day new) and the optional Goodreads cookie browser extension, unchanged (1.0.4): `aleph-goodreads-cookie-1.0.4-chrome.zip` for Chrome, Edge and Brave, and for Firefox the signed `.xpi` (drag it onto a Firefox window to install) or `aleph-goodreads-cookie-1.0.4-firefox.zip`. See [Goodreads Cookie Extension](https://github.com/lara-2-ko/aleph.koplugin/wiki/Goodreads-Cookie-Extension).

Tested with KOReader 2026.07.1 on Kindle Paperwhite and Kindle Colorsoft. Not compatible with Zen UI (ZenOS) or Simple UI.

# v1.2.7 · 2026-11-15

# Aleph 1.2.7

Kindle-style search, Aleph in Brazilian Portuguese and Spanish, Settings that fit at any interface size, ready-made wallpapers, and fixes for the issues you reported. Thank you, everyone who opened an issue!

📖 **How to use everything: [the Aleph wiki](https://github.com/lara-2-ko/aleph.koplugin/wiki)**

## Install or update

1. Download **aleph.koplugin.zip** below and extract it.
2. Copy the **aleph.koplugin** folder into KOReader's `plugins` folder, replacing the old one.
3. Restart KOReader.

Your settings, Home layouts, pins and library are kept. → [Installation guide](https://github.com/lara-2-ko/aleph.koplugin/wiki/Installation-Guide) · [Updating](https://github.com/lara-2-ko/aleph.koplugin/wiki/Updating)

> ⚠️ **Not compatible with ZenOS (Zen UI) or Simple UI.** Turn them off in Plugin management before using Aleph.

---

## 🐛 Fixed issues

- **Book margins could not be turned back on after turning them off** — [#3](https://github.com/lara-2-ko/aleph.koplugin/issues/3). Thanks to @tomdolhs, who also found the exact line. The same mistake was fixed in two other places:
  - **Ratings:** tapping a book's current star rating now clears it.
  - **Customize Home:** tapping the selected widget again now unselects it.
- **Settings could not be left at an interface size of 1.2× or more** — [#4](https://github.com/lara-2-ko/aleph.koplugin/issues/4). Thanks to @N9TailedFOX. The page was taller than the screen and its top, with the back arrow, went off screen. Now:
  - **Settings comes in pages:** every Settings page, the main list included, splits into pages when it doesn't fit, with arrows at the bottom.
  - **The back arrow stays visible:** on all of Aleph's full-screen pages, the header stays at the top whatever the size.
  - **Book margins** comes in pages too.

---

## ✨ New

### 🔍 Search like a Kindle
Every match in the book on one page, then a bar to go through them, and a way back to your page. → [Search](https://github.com/lara-2-ko/aleph.koplugin/wiki/Search)

- **The results page:** "46 results", with an **Annotations** tab (your highlights and notes with the words) and a **Text** tab (every match with the lines around it, the word in bold, its chapter and page).
- **The bar:** tap a result to open the book there with the word highlighted. A bar at the foot of the page shows **Page 34 · ‹ Result 1 of 46 › · ×**. Pages still turn as usual, and "Result 1 of 46" brings the list back.
- **Getting back:** when you finish away from where you were reading, **Go to most recent page** takes you back, and **Return to page 53** goes to the result again.
- **KOReader's own search box:** hold the search button on the results page for its options (capitals, whole words, patterns).
- **Turning it off:** Settings → Reader → **Search like a Kindle**.

### 🌎 Português (Brasil) and Español
Aleph follows KOReader's language (Settings → Language). Every screen is now translated into **Brazilian Portuguese** and **Spanish**, and dates use the right month and day names. Portuguese from Portugal and every kind of Spanish use these too. Anyone can add another language. → [Languages](https://github.com/lara-2-ko/aleph.koplugin/wiki/Languages)

### 🖼️ Wallpapers
Five seasonal wallpapers made for Aleph's Home: **Romantic Valentine, Summer Beach, Autumn Enchanted, Christmas Wonderland and Easter Garden**. Download **aleph-wallpapers.zip** below, or pick one from the [wallpapers folder](https://github.com/lara-2-ko/aleph.koplugin/tree/main/wallpapers). Then use Customize Home → **+ Add wallpaper**. → [Wallpaper](https://github.com/lara-2-ko/aleph.koplugin/wiki/Wallpaper#ready-made-wallpapers)

### 📖 Reader menu
- **Search** replaces the Contents button.
- **Table of contents:** tap the **Chapter** line (the chapter and its pages left) to open it.

### ✨ X-Ray Story
A chapter's summary now has one row of buttons, **‹ · The story · Go to chapter · ›**, to move to the summaries before and after it. A sideways swipe does the same. → [X-Ray](https://github.com/lara-2-ko/aleph.koplugin/wiki/X-Ray)

---

## Assets

| File | What it is |
|---|---|
| `aleph.koplugin.zip` | The plugin: extract it and copy the `aleph.koplugin` folder into KOReader's `plugins` |
| `aleph-wallpapers.zip` | The five wallpapers |
| `aleph-goodreads-cookie-1.0.4-chrome.zip` | Optional browser extension for the Goodreads plugin (Chrome, Edge, Brave) |
| `aleph-goodreads-cookie-1.0.4-firefox.zip` / `.xpi` | The same for Firefox (the .xpi is the signed one) |

Full change list: `MODIFICATIONS.md`.

# v1.2.0 · 2026-11-15

# Aleph 1.2.0

A home screen, library and set of reader tools for KOReader, after BookOrbit's. This release brings together everything since 1.1.0, from 60 test builds (1.1.1 to 1.1.60).

📖 **How to use the new features: [the Aleph wiki](https://github.com/lara-2-ko/aleph.koplugin/wiki)**

## Install or update

1. Download **aleph.koplugin.zip** below and extract it.
2. Copy the **aleph.koplugin** folder into KOReader's `plugins` folder. If you are updating, replace the old folder.
3. Restart KOReader.

Your settings, Home layouts, pins and library are kept. → [Installation guide](https://github.com/lara-2-ko/aleph.koplugin/wiki/Installation-Guide) · [Updating](https://github.com/lara-2-ko/aleph.koplugin/wiki/Updating)

**Optional:** the **Aleph Goodreads cookie** browser extension, used only with the Goodreads plugin by advokatb. It renews that plugin's Goodreads sign-in from your computer in one click, instead of finding and typing your cookie by hand.

- `aleph-goodreads-cookie-1.0.4-chrome.zip` is for Chrome, Edge and Brave.
- `aleph-goodreads-cookie-1.0.4-firefox.zip` is for Firefox, or the signed `.xpi`.

→ [Goodreads cookie extension](https://github.com/lara-2-ko/aleph.koplugin/wiki/Goodreads-Cookie-Extension)

> ⚠️ **Not compatible with ZenOS (Zen UI) or Simple UI.** Both replace the same screens as Aleph. Turn them off in Plugin management before using Aleph.

---

## ✨ New on Home

### Literary clock widget
The time told by a line from a book that mentions it. You see the quote for the current minute with the time in bold, and the book's title and author under it. When a minute has several quotes, the choice changes from day to day. Quotes the collection marks as not safe for work are left out.

Add it from Customize Home → + Add widget → Decor. → [Literary clock](https://github.com/lara-2-ko/aleph.koplugin/wiki/Literary-Clock)

### Wallpaper
Customize Home → **+ Add wallpaper** puts a picture from your device behind every page of Home. You can choose:

- **Fit:** Fill (the edges are trimmed) or Whole.
- **Wallpaper opacity**
- **Widget opacity:** widgets can be see-through over the picture.

→ [Wallpaper](https://github.com/lara-2-ko/aleph.koplugin/wiki/Wallpaper)

### Read widget
This widget shows how much of your library you have finished ("37% of your books") over the covers of finished books. Tap it to list every finished book.

### Larger interface sizes
Settings → Home → Interface size now goes from 1× up to **1.5×**, for anyone who finds the text too small. It has nine steps, set with − and +.

### Night profile
**Off by default.** Turn it on in Settings → Home → Night profile to make night mode automatic and look the way you like. While night mode is on:

- The front light changes to **your own night brightness and warmth**. Choose them, or take the light as it is right now.
- Book text gets **a little bolder** (off or three levels), so light letters on black stay crisp.

When night mode turns off, your day light comes back.

**By the clock** turns night mode on and off by itself between two times. **Set them to whatever times you want** (21:00–07:00 is only the starting point). If you switch night mode by hand in between, it stays that way until the next change time.

→ [Night profile](https://github.com/lara-2-ko/aleph.koplugin/wiki/Night-Profile)

### Owner information
**Optional.** If your e-reader is lost, whoever finds it can see how to contact you. Menu → **Owner information** (between Settings and About) holds your name, email and phone number. Fill in only what you want shown. They appear large under "If you find this e-reader, please contact:", and are kept on the device only. → [Owner information](https://github.com/lara-2-ko/aleph.koplugin/wiki/Owner-Information)

### Widget actions
Settings → **Widget actions** sets:

- **The Quick settings widget's buttons:** up to five, each with its action, its icon and its name.
- **What a tap on each widget opens:** its usual page, nothing, or any action.

Actions come from Aleph, KOReader and every installed plugin that offers gesture actions. → [Home screen and widgets](https://github.com/lara-2-ko/aleph.koplugin/wiki/Home-Screen-and-Widgets#widget-actions)

### Smarter book suggestions
- **Discover** offers only books you can start: unread books, and in a series only the next one to read.
- **Up next in series** shows the next book only once the book before it is finished, and only if the next one is still unread.

### Yearly goal
Tap the number to **type your goal** (1 to 100,000) instead of tapping + many times. Home now updates once, after you stop tapping.

---

## 📚 Library and books

### Sorting authors
- **Sort by last name:** both the library's Sort and filter (**Author (by first or last name)**) and the Authors list (First name / Last name / Most books) can sort by surname.
- **How the surname is found:** it is the part before a comma ("Collins, Suzanne"), otherwise the last word. Jr./Sr./II are set aside, and particles such as "Le Guin" and "van Gogh" are kept.

→ [Library and sorting](https://github.com/lara-2-ko/aleph.koplugin/wiki/Library-and-Sorting)

### Extra filters
Language, Pages (under 200 … 600 or more) and Released (by decade). They are opt-in under Settings → Library → Extra filters, because Aleph reads every book's details once.

### Book details
- **Half-star ratings:** tap the left half of a star for a half star.
- **Language** is shown by name ("English") instead of a code ("en-US", "eng").
- **Page count:** from Calibre's page-count column when there is one, otherwise KOReader's own count.

### Deleting books
- **Delete a book from its page:** ⋯ → Delete book offers two ways. *keep its data* deletes only the file (highlights and progress stay). *and its data* deletes everything.
- **Finished books stay counted after deleting them.** Your yearly goal and the Finished this year shelf keep them. Tap a deleted book there to see when you finished it or to remove it from the record.

### Covers
Settings → Library → Covers: **Whole** (each cover at its own shape), **Fill** (every cover the same size, trimmed) or **Stretch**.

### Settings → Library
Library folders is now **Library**. It holds the folders, refresh, Covers, Extra filters and the Goodreads options.

---

## 📖 Reading

### Coloured bookmarks, as in the Kindle app
- **Colours:** Red, Orange, Yellow, Green, Aqua, Blue, Purple and Pink.
- **The page's corner** shows a ribbon in the bookmark's colour (grey shades on black-and-white screens).
- **Bookmarking a page** opens a list of colours under the ribbon. Bookmarking from the page's corner or a gesture works too (this was fixed in 1.1.36).
- **Filtering by colour:** the bookmarks page's colour dots show the bookmarks of that colour. On the **All** tab, a highlight colour also shows bookmarks of the same colour.
- **To skip the colour list:** turn off Settings → Reader → Choose a colour when bookmarking.

→ [Coloured bookmarks](https://github.com/lara-2-ko/aleph.koplugin/wiki/Coloured-Bookmarks)

### X-Ray, Aleph's own
Turn it on in Settings → X-Ray (it is off by default). It lists the **people, places and other names** of the book and where each was mentioned **up to your page**. It finds them on the device, with no network. The card for each name shows its spellings, counts and every mention with the words around it.

Optional, with your own Claude, OpenAI, Gemini or OpenAI-style key:

- **Describe with AI:** what each name is, with People / Places / Other filters.
- **Story:** chapter summaries and "the story so far", written only from what you have read.
- **The book before:** a recap of the previous book in the series.
- **Recap after a break:** offered when you come back to a book after a while.

→ [X-Ray](https://github.com/lara-2-ko/aleph.koplugin/wiki/X-Ray)

### Page turner battery
With **BT Manager / HID Passthrough** and a Bluetooth page turner, the page's bottom line ends with a dot, the Bluetooth mark and the page turner's battery (**" · 80%"**). It appears only while a page turner reports its battery, and shows up with the first page it turns. → [Book margins and page turner battery](https://github.com/lara-2-ko/aleph.koplugin/wiki/Book-Margins-and-Page-Turner-Battery)

### Reader menu
- **Settings → Reader** is a new category. It holds Reader menu at the bottom, Page browser on swipe up, Pinned pages and bookmark colours.
- **The cover** in the reader menu opens the book's page.
- **Plugin buttons:** with Syncery or KOSyncthing+, a **Sync now** button. With the Goodreads plugin, a **Goodreads** button that sends your reading progress.

### Extra highlight styles
Styles added by a patch or a modified KOReader (Crosshatch, Wavy underline, Outline thick and others) appear in the Highlight sheet and the bookmark filters.

---

## 🔄 Sync and Goodreads
All of these are optional and appear only with those plugins installed.

### Sync both e-readers in one tap
With **KOSyncthing+** and **Syncery**, the Quick settings Sync button and the reader menu's Sync now run the whole chain, step by step, with a Stop button:

1. Wi-Fi
2. Syncthing
3. Syncery
4. Waiting for the other e-reader
5. The files exchanged both ways
6. The jump offer, or a library refresh

Syncery's **cloud** (Dropbox, WebDAV, FTP) is followed too. The other e-reader's progress shows in the library and on book pages ("60% on Colorsoft"). → [Sync two e-readers](https://github.com/lara-2-ko/aleph.koplugin/wiki/Sync-Two-E-Readers)

### Import from Goodreads
Settings → Library → **Import from Goodreads** reads your Goodreads library export (`goodreads_library_export.csv`). It shows what it would change before changing anything.

- **What it fills in:** statuses, finished dates and ratings, but only where they are empty.
- **When finished dates differ:** **Choose finished dates** lets you keep this device's day or Goodreads' day, for each book or for all at once.
- **Books read on Goodreads but not on the device** count toward that year's goal.
- **Importing again** never adds anything twice.

→ [Goodreads](https://github.com/lara-2-ko/aleph.koplugin/wiki/Goodreads#import-from-goodreads)

### Send to Goodreads
A book's page → ⋯ → **Send to Goodreads** sends its status, plus its rating and finished date for a finished book. The book doesn't need to be open, and you confirm before anything is sent.

### Goodreads tracking in the background
Settings → Library → **Track in the background** is off unless turned on. Aleph makes the Goodreads plugin's automatic updates in a background process, so turning a page or closing a book never waits for goodreads.com. That wait could be up to 45 seconds on Wi-Fi without internet.

### Goodreads sign-in, without copying cookies by hand
**Why:** the Goodreads plugin signs in to goodreads.com with your browser's **cookies**, and its sign-in expires from time to time. Until now, renewing it meant:

1. opening the browser's developer tools on a computer;
2. finding the right request;
3. copying a long, unreadable "Cookie" line;
4. getting it onto the e-reader and pasting or typing it in without a single mistake.

That was fiddly, easy to get wrong, and hard to do at all without a computer background.

**Now it takes a few seconds:**

1. On the e-reader, open Settings → Library → **Goodreads sign-in** (under Import from Goodreads). It shows an address and a four-digit code.
2. On a computer signed in to goodreads.com, click the **Aleph Goodreads cookie** browser extension, enter the address and code, and press **Send**.

The extension picks up the cookies by itself and sends them straight to the e-reader over your home network. Aleph saves them in the Goodreads plugin's settings, and the plugin is signed in again. Nothing to find, copy or type.

The e-reader listens only while that screen is open, for at most 10 minutes. The four-digit code keeps other devices out.

→ [Goodreads cookie extension](https://github.com/lara-2-ko/aleph.koplugin/wiki/Goodreads-Cookie-Extension)

---

## 🎛️ Buttons and keys
- **Page-turn buttons** (Kobo Libra, Kindle Oasis, a keyboard) turn the pages of Home, the library, authors, series and a book's neighbours.
- **Direction keys** (Kindle 4, keyboard Kindles) move a mark between everything that can be tapped on Aleph's screens, and Press taps it. This is on by itself on devices with those keys; turn it on elsewhere with Settings → About → Button navigation.

→ [Buttons and gestures](https://github.com/lara-2-ko/aleph.koplugin/wiki/Buttons-and-Gestures)

---

## ⚡ Faster and steadier
- **Changing books and quitting KOReader** no longer wait several seconds while the library index is saved. It is written in the background, and on quitting.
- **The library is read once per session** and shared. The book you close is read again on its own, so its progress is right at once.
- **Covers and author portraits** are made in a background process.
- **Home's lists** are kept between refreshes instead of being sorted again many times.
- **Clock widgets** (Clock, Analog, Literary) redraw only themselves each minute, instead of the whole of Home. The minute tick stops when no clock is shown.
- **Rotating the screen** redraws Home at once.
- **Settings pages** too tall for the screen come in pages instead of being cut off.
- **Filter lists** fit their contents (long lists split into two even columns).

## 🛠️ Fixes
- **New highlights** sometimes came out yellow whatever colour was picked.
- **Opening Sort and filter** crashed with some libraries.
- **The bookmark colour list** didn't appear when bookmarking from the page's corner.
- **The reader menu's Bookmark this page switch** never moved.
- **Aleph's reader menu** now closes when a top-menu item opens. Before, it hid plugins such as Capitulares.
- **Aleph Home and All books** from the reader menu now leave the book properly.
- **X-Ray:** Describe with AI no longer gives up after 20 seconds. "The book is closed" no longer appears with the book open.
- **The Goodreads sign-in screen** now works when the browser keeps extensions off the local network.

## 🔍 Troubleshooting
- **Failures caught by Aleph** are now written to `crash.log` as `Aleph: file.lua:line failed: …` lines, once each. Before, they were silent.
- **For problems opening a book:** Settings → About → **Troubleshooting log**.

→ [Troubleshooting](https://github.com/lara-2-ko/aleph.koplugin/wiki/Troubleshooting)

## Notes
- **Literary clock quotes:** from the Literature Clock collection (The Guardian's readers, JohannesNE, Carlos Bonadeo), as converted by readinpixels' Literary Clock. They are shared under **CC BY-NC-SA 2.5** (non-commercial); see `THIRD_PARTY_NOTICES.md`.
- **New icons:** from Lucide (ISC).
- **Full change list:** `MODIFICATIONS.md`.

## Assets
| File | What it is |
|---|---|
| `aleph.koplugin.zip` | The plugin: extract and copy the `aleph.koplugin` folder into KOReader's `plugins` |
| `aleph-goodreads-cookie-1.0.4-chrome.zip` | Browser extension for Chrome, Edge and Brave (Load unpacked) |
| `aleph-goodreads-cookie-1.0.4-firefox.zip` / `.xpi` | Browser extension for Firefox (the .xpi is the signed one) |

# v1.1.0 · 2026-11-10

## Aleph 1.1.0

### New
- **Reader menu shortcuts:** a Bluetooth switch for **BT Manager - HID Passthrough**, plus **Sync now** and **Progress** for **Syncery**. Each one only appears when that plugin is installed.
- **Book margins:** choose the text colour (Light gray, Gray, Black, or any colour on colour screens) and Regular or Bold text, and move the top and bottom lines closer to or further from the edge.
- **Comics:** CBZ, CBR, CB7 and CBT files now show their real title, series and issue number, writers, genres and summary, read from the `ComicInfo.xml` inside them.
- **Custom metadata** set in KOReader (Book information → Set custom) is now used throughout the library.
- **Highlight menu:** smaller and tidier, with a new **Pin** button. **More** now has a **Back** button.
- **Warning at startup** when ZenOS or Simple UI is also running. They replace the same screens as Aleph and can freeze KOReader.

### Fixes
- Comics marked Reading or Finished no longer disappear from the Series view or lose their titles.
- The bottom margin text no longer sits too high when KOReader's status bar is on but empty.
- **Highlight** in the dictionary pop-up now highlights the word and closes the pop-up. Before, it seemed to do nothing.
- The top menu's brightness and warmth slider no longer touches the − and + buttons.
- Wikipedia now has its own "W" icon.

### Install
Download **aleph.koplugin.zip** below, extract it and copy the `aleph.koplugin` folder into KOReader's `plugins` folder, replacing the old one. Then restart KOReader. Storefront users will get the update automatically.

Not compatible with ZenOS or Simple UI. See the README for which other plugins work alongside Aleph.

# v1.0.1 · 2026-11-10

A small update with two fixes.

## Fixes

- **Night mode:** a book with a page colour chosen in **Style → Background** could turn white in night mode and flash on every page turn. In night mode, pages now use KOReader's normal colour, so they stay dark, and your chosen colour comes back when night mode is off. Colours too dark to read on can no longer be picked as a page colour.
- **Top menu:** the round check marks no longer touch the text next to them.

## Updating

Replace the `aleph.koplugin` folder in KOReader's `plugins` folder with the one in **aleph.koplugin.zip** below, then restart KOReader. Your settings and data are kept. If you installed through Storefront, you can update from there.
