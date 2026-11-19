# v2.6 · 2026-11-19

# ennUI 2.6

A minimal, text-based home screen for KOReader.

## Install
Copy the `ennui.koplugin` folder into KOReader's `plugins` folder (replacing your
current version) and restart KOReader. Disable any other home screen plugin (for
example Simple UI) while using ennUI. Your existing settings carry over.

## What's new in 2.6
- **The gear menu no longer cuts its words.** The pop-up now sizes itself to its buttons: it is never
  narrower than before, and grows only as wide as the labels need, up to nearly the whole screen. Each
  button is as wide as its own label and icon (as before), so "ennUI settings" gets the most room. If the
  labels still would not fit, the text shrinks a point at a time (down to about 60%) before anything is cut.
- **Full color pickers on color e-readers.** Where the screen is a color screen *and* KOReader's color
  rendering is on, every color picker (text color, drop shadow / outline / glow color, and the three Module
  Rack colors) replaces its gray bar with three: **Hue**, **Saturation** and **Brightness**, each with - and
  + buttons (5 degrees or 5 percent at a time), a bar you can tap to jump, a swatch and a label. The opacity
  bar stays. A color with no color in it (saturation or brightness at zero) is saved as the gray level it
  always was; anything else is saved as `#RRGGBB`. **Copy color to...** and Homescreen / Module Rack presets
  carry full colors. On any other device nothing changes: the gray bar is used, and a saved color is drawn as
  its nearest gray (and stays saved, so turning color back on brings it back). Gray colors you already chose
  load into the sliders as gray and are left alone until you move one.
- **Extras > Force Color** (off by default): treats the screen as color even if ennUI does not recognise it
  as one, for a color e-reader where the pickers do not appear on their own.
- **Literary clock > Time size** (default +2 pt, 0 to 10): the words that give the time are drawn that many
  points bigger than the rest of the quote. The words share a baseline with the ordinary text, and lines keep
  the spacing of ordinary text, so the bigger words run a little above and below their line and may come
  close to the lines next to them. Words wrap as wide as they really are; at +0 the quote is drawn exactly as
  in 2.5.
- On a color screen, a see-through outline now keeps its color (it was being flattened to gray).
- Version 2.6.

## From 2.5 (still true unless 2.6 says otherwise above)
- **The Module Rack's System and Reading stats cards open their plugins.** The debug log showed why they
  didn't: on the device the plugins' ids carry a "filemanager" prefix (`filemanagerstatistics|statistics`,
  `filemanagerbatterystat|battery_statistics`, `filemanagerreadinginsights|reading_insights_popup`) and
  ennUI had guessed names without it. The cards now find each plugin by its menu key (the part after the
  "|"), so the prefix doesn't matter. **System** opens Battery statistics. **Reading stats** opens
  **Reading Insights** by default, falling back to **Reading statistics** if Insights isn't installed; a
  plugin picked under Reading stats > Tap opens still comes first. Both open the plugin's own menu list, as
  the home entries do. If nothing can be opened, a message names what to turn on.
- **Restart and Quit have the KOReader logo** beside them in the gear menu, as a one-colour silhouette
  (the book shape with the K and O as holes) drawn in black, or white when the button is filled. If the
  logo file can't be read, a plain symbol is used.
- **Clock > Time in quotes** (Literary clock): As written (default), Digits or Spelled out. The words
  that give the time inside the quote are rewritten from the minute being shown: Digits gives 12-hour
  numbers ("2:15 PM", following Show AM/PM), Spelled out gives "a quarter past two", "half past two",
  "a quarter to three", "noon", "midnight", "nine o'clock", and otherwise the numbers in words ("two
  forty-seven", "two oh five"). They stay bold; a capital at the start is kept. Note that some quotes say
  "nearly three" for a minute that isn't exact; Digits and Spelled out make the time exact.
- **Clock > Hide 24-hour quotes** (Literary clock, off by default): leaves out quotes whose time is an
  unmistakable 24-hour form: an hour from 13 to 23 in digits ("17:45", "1745 hours"), "hundred hours"
  forms, or "zero" forms. Times that could be either clock ("08:30") are never hidden. About 90 of the
  3,626 quotes in the project's file are hidden by this; a minute whose only quote is hidden shows the
  ordinary clock.
- **Copy color to...** replaces Copy color / Paste color. On a Text Style Color screen and on a Drop Shadow
  / Outline / Glow Color screen, a "Copy color to..." row opens a checklist of the other home screen items
  that are switched on (the Module Rack is not included); tap rows to tick them and press Save to give the
  ticked items just this screen's color and opacity (a text color goes to their text, an effect color to
  their outline / shadow / glow color; each item's effect mode is left as it is). Cancel changes nothing.
  The checklist is touch-only.
- Version 2.5.

## From 2.4 (still true unless 2.5 or 2.6 says otherwise above)
- **Literary clock.** Settings > Clock > Clock style: Digital (as before) or Literary. The literary clock
  shows the time as a passage from a book that mentions that exact minute, the words that give the time
  in bold and the title and author underneath, in the clock's own typeface, color, alignment and
  outline / drop shadow / glow settings. The quote is laid out in the biggest text that fits its box.
- **The quotes are not in the plugin.** They are read from `litclock_annotated.csv` in the ennUI plugin
  folder. Settings > Clock > Download quotes fetches it over Wi-Fi from the Literature Clock project's
  own page (https://github.com/JohsEnevoldsen/literature-clock, based on Jaap Meijers' work), or you can
  put a file in that format there yourself: one quote per line, six columns separated by `|`, no header
  (time, the words that give the time, the passage, title, author, content flag). The download is
  checked before it replaces anything, so a failed one changes nothing. Those quotes are excerpts from
  copyrighted books; the plugin does not carry or repost them, and the project's own license terms are
  the project's to state (check them if you share anything built from the file). Settings credit the
  project.
- **Clock size** (Clock settings, Literary only): the share of the screen's *height* the clock takes
  (10 to 90%, default 30%), across the section's full width. The quote's text is sized to fill it, so
  the rest of the home screen never moves when the quote changes.
- **Refresh.** By default the quote changes when the home screen is tapped or the device wakes, exactly
  like the digital clock. **Update every minute** switches it to redraw the clock area by itself at the
  start of each minute while the home screen is up (it stops when you leave or the device sleeps).
- **Show mature quotes** (off by default): quotes the file marks as nsfw are skipped unless this is on.
  Quotes marked "unknown" are shown.
- **No quote, no file or an error** shows the ordinary clock time in the same box; nothing breaks.
- **The gear menu has no blank space any more:** the header sits directly over the three buttons.

## From 2.3 (still true unless 2.4, 2.5 or 2.6 says otherwise above)
- **Fixed: 2.2 crashed at startup when a theme used Glow.** The new glow cache wrote a size note onto
  each stored halo image, and KOReader's image buffers raise an error when you give them a field of
  their own, so the first glowing line painted at startup stopped KOReader. The sizes are now kept in a
  separate list. (My test buffers were plain tables and let the write through; they now behave like the
  real ones, and the test that would have caught this runs with them.)
- **A glow can no longer take the screen down.** If drawing a halo fails for any reason (text or cover),
  the failure goes to the log (and the debug log) and the text or cover is drawn without its glow.
- **The debug module no longer needs KOReader's `ui/time`.** If an older KOReader doesn't have it,
  whole seconds from the system clock are used instead (the five-tap unlock works the same).
- Nothing else changes from 2.2: the glow looks the same, is cached, and goes up to radius 20.

## From 2.2 (still true unless 2.3 or 2.4 says otherwise above)
- **Glow is much quicker.** The finished halo of each glowing line is remembered and reused, so a
  line whose text, typeface, size, spacing, radius, strength and see-through setting haven't changed
  is redrawn with one blit instead of hundreds of paints. Up to 16 halos (and about 3 MB) are
  kept; the oldest go first. The first draw after a change costs what it did before. The look is
  identical.
- **Glow radius goes up to 20** (default still 4). It is still drawn with 16 copies of the text per
  ring, so past about radius 10 the halo can look speckled, but the first draw stays quick.
- **Secret debug mode.** In Settings > About, tap "ennUI version" five times quickly (each tap
  within 2 seconds of the last): a message says debug mode is on and the version row shows
  "· debug". Five quick taps again turn it off. While it is on, ennUI writes to
  `ennui_debug.log` in the ennUI plugin folder: every tap and what it triggered (settings rows and
  tabs, pop-up buttons, home entries, covers, rack cards), calls into other plugins and what came
  back (including the exact plugin id and whether the stats and battery calls ran), and every
  error and note ennUI sends to KOReader's log. Each line has the time. The file is kept under
  about 200 KB (oldest lines dropped), starts empty each time debug mode is switched on, and debug
  mode switches itself off on every KOReader restart. Nothing is written while it is off.
- **The gear menu** is now a pop-up card with its name ("ennUI") in the header strip and, along the
  footer, one row of three buttons separated by slants, like CANCEL / APPLY: "ennUI Settings" (in
  full), then Restart and Quit, each with a one-colour KOReader icon that turns white when the
  button is filled. The buttons' widths follow what they say. Nothing is filled until you tap a
  button or, with hardware buttons, press Left / Right (the first press fills the first or last).
  If a KOReader icon is missing a plain character is used. If the card can't be built, KOReader's
  own button list is used instead.
- **Pop-up cards are 15% smaller overall:** the card, the text, the buttons and the padding.
- **Titles in the header strip.** Every pop-up's name now sits in the header strip beside the dark
  tab, with the thin line carrying on after it. Rack pop-ups show the module's name ("Vocabulary",
  "Highlights") and keep the body as it was. Pop-ups with a title of their own (Font size and the
  other number pickers, Book Cover check...) move it up into the strip. A message with no separate
  title keeps its first sentence as the body's bold line and gets "Notice" (or "Confirm") in the
  strip.
- **Settings redesigned.**
  - The main screen's three groups, General, Layout and About, are tabs along the bottom in the same
    slanted style, the open one filled black. Tap a tab, or swipe sideways on a one-page tab, to
    move between them.
  - The header strip carries the screen's name: "ennUI Settings" on the main screen only; a screen
    such as Date shows "Date". The big "ennUI Settings" title under the strip is gone from every
    page, and so are the card header rows that repeated each screen's name.
  - The page-turn arrows are gone everywhere (the settings lists, the plugin entries list). Pages
    turn by swiping sideways (or the page keys). A tab or screen that fits one screen has no pages.
- **Unchanged on purpose:** the System and Reading stats cards, until the debug log shows the plugin
  ids your device really uses. To find them: switch debug mode on, add Reading statistics and Battery
  statistics as plugin entries on the home screen, tap them, and read the log.

## From 2.1 (still true unless 2.2 or 2.3 says otherwise above)
- **Fixed: letters cut off at the edges when opacity is below 100%.** See-through text (and its
  outline or shadow) is blended from a copy of the screen that was cropped to the text's own box,
  and the ends of script and italic letters reach past that box. The copy is now a little bigger
  on every side. (This follows from reading the code; it has not been checked on the device.)
- **Fixed: the typing box behind the number pop-up.** The pop-up counts as a "modal" window and
  KOReader opens ordinary windows under those; the box is now modal too, so it opens on top.
- **The Vocabulary pop-up scrolls.** An entry too tall for the pop-up is shown whole, and you swipe
  up or down on it to move through it (a thin bar at the right edge shows where you are). With
  hardware buttons, Up / Down scroll. The sentence the word came from is shown in full when it
  scrolls (without scrolling it is still cut at three lines). A plain-text definition scrolls too.
- **The gear / swipe-up menu looks like the pop-ups.** A card with the same header tab, titled
  "ennUI", and the entries (ennUI Settings, Restart KOReader where available, Quit KOReader) as
  rows inside it. The first row starts filled, like the main button of a dialog; tap a row to
  choose it. With hardware buttons Up / Down move the filled row and the centre button chooses.
  Back or a tap outside the card closes it. (Other lists of buttons, such as a preset's
  Apply / Rename / Overwrite / Delete, still use KOReader's own look.)
- **Glow**, a third mode next to Outline and Drop Shadow everywhere those appear (every text item,
  and the Book Cover module). It is a soft halo round the letters in the effect color, strongest
  at the letters and fading out; the color and its opacity are the same settings as for the other
  two, and a new Radius (1 to 20 from 2.2, default 4) sets how far it reaches. With see-through text the
  halo is only outside the letters. Like Outline, it reserves room round the text (the radius on
  each side). On covers the halo is drawn as faint rings, which needs the blending the see-through
  covers already use; where that is not available the cover is drawn without a halo. The menu is
  now called Drop Shadow / Outline / Glow.
- **Tapping the System card opens KOReader's Battery statistics.** It calls the Battery statistics
  plugin directly and, failing that, opens its entry from the plugin menu. If the plugin is off, a
  message says so.
- **Tapping the Reading stats card.** Still Reading progress by default, now tried two ways (the
  Statistics plugin's own call, then its entry in the plugin menu), and if neither works the
  message shows what went wrong instead of nothing happening. I could not find from the code alone
  why it failed on your device, so if it still does, the message (and the log) is what I need.
- **Reading stats > Tap opens:** pick any installed plugin to open when the card is tapped (the
  same list as Add or remove plugins), or the default, Reading progress. A pick that is not
  available falls back to Reading progress with a message. It is not part of presets.

## From 2.0 (still true unless 2.1 or 2.2 says otherwise above)
- **Vocabulary definitions are laid out like a dictionary entry.**
  - *Pop-up (tap the card):* the word is the big bold title. If the definition has one part of
    speech, it sits beside the title in small dim text; with several (Noun, Verb, ...) each gets
    its own dim header line and its own list. Meanings are numbered 1, 2, 3 with the text hanging
    in from the number (wrapped lines line up under the text). A label at the start of a meaning,
    such as "(falconry)" or "(countable)", is dimmed. A part of speech with one meaning has no
    number. Sub-meanings (a, b) show only where the dictionary text marks them like that. Then the
    sentence the word came from, then the book as the dim source line. If the entry is too long for
    the pop-up, the last meaning that fits is cut with "…".
  - *Rack card:* the word in normal weight (no longer big and bold) with its part of speech in
    small dim text after it, the rule, then only the first meaning, then the book line. Tapping the
    card still opens the whole entry; long press still picks another word.
  - The definition arrives as one line of text, so it is split by looking for a part-of-speech word
    (Noun, Verb, Adjective, Adverb, ...) at the start or after the end of a sentence, numbered
    meanings if the text has them, and otherwise one meaning per sentence ("etc.", "e.g.", initials
    and "..." do not end a sentence). Text that does not look like a dictionary entry (no part of
    speech, no numbering or labels) is shown as plain text, exactly as in 1.9. Dictionaries that
    write their entries in another way may split in the wrong place or not at all; the entry is
    then still shown whole.
- **Outline is a stroke when the text is see-through.** With the text color's opacity below 100%,
  the outline used to leave a solid fill of the outline color under the letters, which showed
  through. Now only the ring just outside the letters is drawn, in the outline color at the
  outline's own opacity, and nothing under the letters. At 100% text opacity nothing changed (and
  nothing got slower). The see-through case does one pass over every pixel of each outlined line,
  so it costs more than before; how much on a Paperwhite is not known. Drop shadows are unchanged.
- **Settings screens take on the pop-up look** (they are still full screens): the header band
  with the black slanted tab and a white settings icon, the thin line across the top ending at
  the X, a rule under it, then "ennUI Settings" as a big bold line; cards with the pop-up's heavy
  rounded border; the color screen's - and + buttons with the same heavier border. Rows look as
  before. The band is shared with the pop-ups, so the two stay the same. It takes a little more
  room than the old title bar: the main Settings screen's rows shrink a bit more to stay on one
  page, and a long list may show one row fewer per page. With hardware buttons, a focused row is
  inverted inside the card's border rather than over it.
- **Wallpaper: Darken / Lighten** (was Lighten). One number from -100% to +100%: 0% leaves the
  picture alone, below 0 fades it toward black (-100% is pure black), above 0 toward white (+100%
  is pure white). Saved values carry over. Text keeps its own color and opacity and is blended
  with the adjusted picture, so a dark wallpaper with the default black text is hard to read:
  change the text colors in Text Style.
- **Number pop-ups: tap the number to type it** (this was lost in 1.9). Tapping the big number
  opens KOReader's own entry box ("Enter number", number keyboard, hint like "22 (8 - 200)",
  Cancel and OK). A number out of range keeps the box open and says "This value should be X or more"
  or "Y or less"; it does not snap. OK puts the number in the picker; Apply still saves it and
  Cancel throws it away. The number has no underline or other mark. With hardware buttons the
  centre button does not open the box. The old picker's "=" arithmetic and ":" range tricks are
  not included. Decimals are rounded for whole-number pickers.
- **Long press on the Module Rack panel in Build Mode** (on any part that is not a card) opens
  the Module Rack settings page on top of the rack. With Build Mode off, or outside the panel,
  nothing happens. Cards keep their own long presses.

## From 1.9 (still true unless 2.0 or 2.1 says otherwise above)
- **Plugin entries.** "Add or remove plugins" is gone from the Plugin entries page; it is still
  the first row inside **Edit entries**. Every entry row on the home screen is now exactly
  the same height and its text sits on the same baseline, so the lines are evenly spaced
  whatever a label contains (a "g" or a bracket no longer pushes its neighbours). Row spacing
  works as before, including below 0.
- **Book Cover module.**
  - **Vertical layout** now shrinks the covers when the height left under the sections above
    can't hold a stack: at least three covers (or all of them, if fewer are wanted) always
    stack top to bottom, down to a minimum cover height of 24 px. It used to fall back to one
    cover per column, which looked horizontal.
  - **Recently added** looks for new books once per KOReader launch instead of every 6 hours.
    The list saved last time is shown straight away while the scan runs, and the home screen is
    only redrawn if the scan found something different. If no home folder has been set in
    KOReader, the folder it starts in is used.
  - **Check Recently added** (new row under Books shown) shows which list is chosen, the folder
    looked in, whether it was scanned this launch, the five newest files found with their dates,
    and the first five active books for comparison. The same facts go to KOReader's log
    (`crash.log`, lines starting "ennui:"). This is how to find out why the two lists look alike:
    the cause was not found by reading the code.
- **Module Rack.**
  - **Reading stats tap** opens KOReader's own Reading progress. Reading Insights is no longer
    tried (it could report success without showing anything). If Reading progress can't be
    opened, a message says so instead of nothing happening, and the log says why.
  - **Vocabulary card:** the word is big and bold, then a rule, the definition and the book as a
    small dim line. Long-pressing now picks among the *other* words (it used to draw again and
    hope), and each long press is written to the log with how many words it picked from. With
    only one word that has a saved definition, the same word comes up again; that is the "only
    words with a definition" rule, unchanged.
  - **Opacity on all three colors** (see below). The old "Background opacity" row is gone from
    the Colors page: the same setting is now on the Background color screen.
- **Settings access** has a third choice, **Both**: the gear shows and the upward swipe from
  the bottom edge opens the menu too. Extras cycles Gear icon, Swipe up from bottom, Both. The
  gear's own row in Settings is only greyed out in swipe-only mode. The first-run text and the
  one-time reminder follow the mode.
- **Opacity.** Every color screen (text colors, outline and shadow colors, the three rack colors)
  has a second row under the shade bar: **- and +** step the opacity through 0 to 100% in tens,
  tapping the bar jumps to that spot, and the swatch shows the color as it will look over white.
  - Home screen text, outlines and shadows are blended with whatever is behind them, the
    wallpaper included. At 100% (the default) nothing extra is done, so nothing gets slower.
    Below 100% each affected piece of text is drawn into a scratch buffer and blended back, which
    costs a little time on each repaint.
  - Book Cover outlines and drop shadows are blended the same way as the rack panel.
  - Rack: Background blends the panel with the home screen, Cards blends each card with the
    panel, Font blends the text, borders and bars with the card. The panel's own edge line stays
    solid. Colors saved with an opacity travel with presets.
  - If the device can't blend, the opacity row says "Not supported on this device" and colors stay
    solid. The Vocabulary card's rule and the rack's bars follow the Font opacity.
- **Pop-ups.** Every ennUI dialog and message has one new look: a rounded card with a heavy
  border, a black header tab with a slanted edge and a white KOReader icon that suits the
  pop-up, a thin line along the top, a rule, a big bold title, smaller body text, an optional dim
  source line and bold capital buttons. One button is plain and full width; two are split by a
  diagonal; three or more have a diagonal between each pair. A filled button is the focused
  one: on a touch screen the main action starts filled, and with hardware buttons the filled
  one moves. Pop-ups without buttons have no footer and go away when tapped or after their
  timeout. Number pickers are the same card with - and + buttons (long press for the bigger
  step) and a "Default" line. Menus (the gear menu, the preset action list) and KOReader's own
  keyboard box (used to type a ZIP code or a name) keep their usual look.
- **Hardware buttons.** On a device that reports a D-pad or keys (nothing changes on a touch-only
  device): Up, Down, Left and Right move a focus (drawn inverted) between the tappable things on
  every ennUI screen; the centre button taps, and holding it for about a second long-presses
  (Shift + centre long-presses at once). On the home screen it starts on the first entry; pushing
  past the first or last entry turns the page; pushing toward the Module Rack's side with nothing
  further that way opens the rack; Menu opens the gear menu; Back closes an open folder. In the
  rack the focus moves between cards and pushing toward its edge closes it. On lists, the focus
  moves over rows, the X and the page arrows. In pop-ups left and right move the filled button
  and the centre button chooses it; in number pickers up and down change the number.
- Version numbers use two digits (1.9).

## From 1.8 (still true unless 1.9, 2.0 or 2.1 says otherwise above)
- **Settings gear.** Settings can now be reached with a gear icon laid over the top of the
  home screen, using KOReader's own `appbar.settings` icon. It takes no room, so nothing
  else on the screen moves.
  - **Extras > Settings access** switches between **Gear icon** and **Swipe up from
    bottom**. A new install starts with the gear; an install that was already set up keeps
    the swipe. That is decided once, the first time ennUI runs 1.8, and saved.
  - The gear has its own row in Settings (General > **Settings gear**) with Size (24 to
    120, default 48, a width on a 758px screen), Alignment (default right) and Padding.
    There is no Enabled switch and it is not in Section order. Size and padding are kept
    so the gear is always fully on screen. In swipe mode the row is greyed out.
  - Tap the gear for the usual menu (ennUI Settings, Restart KOReader, Quit KOReader).
    With Build Mode on, long-press it to open its settings. In gear mode the swipe up
    from the bottom edge is ignored, so KOReader's own gestures work there.
  - The first-run text and the one-time reminder follow the chosen mode.
  - Tools > ennUI is unchanged: it opens the home screen.
- **Plugin entries.** Row spacing now goes from -40 to 40 (still 9 by default; nothing
  about how entries look at 0 and above has changed). Below 0 the rows are squeezed
  closer together than their text, never to less than 6 pixels tall. Each tap area is at
  least as tall as its text; where squeezed rows' tap areas overlap, a tap goes to the row
  nearest your finger.
- **Book Cover module** (was "Recent books"; the setting key is still `covers`).
  - **Books shown:** *Active books* (opened before and not marked complete or on hold,
    newest first) or *Recently added books* (the newest files in your home folder, by the
    later of each file's change time and modification time). The recently added list
    comes from a background walk of your library (saved in `cache/ennui_recent_files.lua`);
    since 1.9 it runs once per KOReader launch. Until the first walk has finished, nothing
    is shown.
  - **Layout:** *Horizontal* is as before (wrapping onto two rows at most). *Vertical*
    stacks covers top to bottom in up to two columns, as many as fit in the screen
    height left below the sections above them. Put the module last in Section order if
    you want the other sections to keep their room.
  - **Spacing** (-100 to 100, default 10) is the gap in both directions. Below 0 covers
    overlap, later ones painted on top, and a tap in an overlap goes to the top cover.
    The invisible tap margin is the smaller of 8 pixels and half the gap (none when they
    overlap). Number of covers (up to 12), Cover size (50 to 500) and the 14-book
    thumbnail cache are unchanged; the cache now keeps the first 14 books of the list
    being shown.
- **Module Rack.**
  - **Settings page order:** Enabled, Modules, Side, Width, Edge sensitivity, Colors,
    Font settings.
  - **Colors:** Background, Cards and Font, each with the usual color screen (white, white
    and black by default), and **Background opacity** (0 to 100, default 100). Borders and
    bars use the Font color; dim text is halfway between the Font and Card colors. The
    cards used to stay solid; since 1.9 each color has its own opacity (see above). The panel is
    blended with the home screen smoothly (no dithering). If the device can't do that, the panel stays solid and the
    opacity row says so. Under a see-through panel the home screen is repainted first on
    every paint, so repaints never stack. (The 1.6 removal of opacity for text and covers is
    reversed by the new opacity in 1.9, which blends against the wallpaper.)
  - **Loading rule:** every slow module loads once at first use, then at most once every
    24 hours, or when you long-press its card. "Loading…" only shows on the very first
    load or a forced refresh; whatever is on screen stays while a daily refresh runs and
    is then swapped. System stays live.
  - **Reading stats** keep their last saved set whatever its age (so the card never goes
    blank) and say "Updated … ago". The current book is still read fresh. **Tap** opens
    KOReader's own Reading progress (since 1.9). **Long-press** refreshes.
  - **Highlights:** one is picked when the rack opens. The index is brought up to date at
    most once a day. **Tap** shows the full text, your note and the book, with **Open
    book** (opens the book at your last position, not at the highlight) and **Close**.
    **Long-press** picks another.
  - **Vocabulary** (new; add it under Modules, it is not on by default): a random word
    from the Vocabulary Builder with its definition and "— book". The Vocabulary
    Builder doesn't keep definitions, so a daily background job looks up to 200 words in
    KOReader's dictionary, one per tick, and saves them in `cache/ennui_definitions.lua`.
    It stops without counting as done if no dictionary is available, and a word with no
    result is tried again after a week. Only words with a saved definition are picked;
    before any exist it shows words with "Looking up definitions…". **Tap** shows the
    definition, the sentence and the book; **long-press** picks another word. Maximum lines
    (default 5) is in the module's options.
- **Presets.** Presets is now **Homescreen Presets** (it also holds the gear's size,
  alignment and padding and the new Book Cover options, but not Settings access). New:
  **Module Rack presets**, with the same flow (Default first; save, apply with a
  confirmation, rename, overwrite, delete) and their own list. They hold side, width,
  modules, the three colors, opacity, both typefaces and sizes, the System options, the
  stats rows and the highlight and vocabulary line counts, but not Enabled or Edge
  sensitivity. Extras order: Build Mode, Settings access, Homescreen Presets, Module Rack
  presets, Refresh cover cache.
- **Typeface lists** (every one, including Text Style) draw each name in its own
  typeface. Faces are only built for the rows on the page.
- Everything else from 1.7 works as before. The main Settings page still fits on one
  page (its rows shrink a few percent to make room for the Settings gear row).

## Not tried on a device yet
This version was built and checked in a stand-in KOReader on a computer (layout, painting, key
handling, opacity blending and the pop-ups were run there), not on a Kindle. New in 2.6 and not yet confirmed on the device: the gear menu
sizing itself, the full-color pickers (they need a color screen), Force Color, and the literary clock's bigger time words. New in 2.5 and not yet confirmed on the device: the rack cards opening their plugins, the logo icons,
the literary clock's time format and 24-hour filter, and Copy color to... New in 2.4 and not yet
confirmed on the device: the literary clock (its look, size and speed, the
download, the once-a-minute option) and the gear menu without its blank space. New in 2.3 and not yet
confirmed on the device: that it starts with Glow on (the crash fix). New in 2.2 and
not yet confirmed on the device: the remembered glow and radius 20, the debug mode
and its log, the three-button gear menu with its icons, the 15% smaller pop-ups, the titles in the
header strips, and the tabbed settings with swipe-only paging. New in 2.1 and not yet confirmed
on the device: the fix for cut-off letters, the
glow (its look and speed on e-ink, and on covers), swiping through a long Vocabulary entry, the
menu pop-up for the gear, the Battery statistics tap, and the Reading stats tap with its
fallbacks and the plugin picker. New in 2.0 and not
yet confirmed on the device: the dictionary-entry layout with your real dictionary's text (the
splitting was tested on made-up strings), the outline stroke (its speed and how the edges look on
e-ink), the new look of the Settings screens (the tab, the heavier borders, and whether the main
Settings screen's shorter rows feel right), the Darken / Lighten look on a real wallpaper, KOReader's
entry box over the number pop-up, and the Build Mode long press on the rack. From 1.9: every part of the hardware-button support (a Paperwhite 2015 has
no buttons, so this was only simulated), the new pop-up look on the e-ink panel (the slanted
tab, the diagonals and the exact icons), opacity on text and in the rack (the blend itself
works in the stand-in; the speed on the device is unknown), the vertical cover stack with a
real library, the Recently added check, the Reading progress tap, the Vocabulary long press
(see the log), and, from 1.8, the see-through rack panel, the gear overlay, dictionary
lookups and the Vocabulary Builder reading, the "Open book" box with a long highlight, the
highlight tap, long-pressing the Book Cover module in Build Mode, and the narrower tap areas.

## If the gear is ever lost
The gear can't be switched off, kept below size 24 or moved off screen, but if Settings
ever can't be reached: open `settings/ennui.lua` (in KOReader's folder) in a text editor
while KOReader is closed, change `["settings_access"] = "gear"` to `"swipe"`, save, and
start KOReader. Then swipe up from the bottom edge of the home screen.

## Use
- Open Settings with the gear icon (or by swiping up from the bottom edge of the home
  screen, if Extras > Settings access is set to swipe), any time.
- Settings lists, in three cards: General (Date, Clock, Weather, Plugin entries, Book
  Cover module, Settings gear), Layout (Section order, Module Rack, Wallpaper, Extras) and
  About (the version). Tapping any of the General entries opens: Enabled, Alignment,
  Padding, Text Style (not for the Book Cover module or the gear), Drop Shadow / Outline
  (not for the gear), plus whatever's specific to that item (the gear has no Enabled):
  - Book Cover module: Books shown, Layout, Number of covers (1 to 12), Cover size (50 to
    500 pixels tall) and Spacing (-100 to 100).
  - Settings gear: Size, Alignment and Padding.
  - Clock: Show AM/PM (the clock is always 12-hour).
  - Weather: ZIP code, country, units, Show last refreshed, Update now. Tap
    the weather line on the home screen to refresh it on the spot (Wi-Fi is
    never turned on for you).
  - Plugin entries: Add or remove plugins (including "Resume current book"
    and File Manager), Edit entries (reorder, rename, folders — tap a folder
    to edit what's inside; folders are one level deep), Row spacing (-40 to 40), Max
    entries per page (shows "Auto-fit to page" when uncapped), and Show page
    number. On the home screen, tapping a folder swaps the list for its
    contents, with a "←" row to return; long-pressing a section (Build Mode
    on) jumps straight to its settings.
- Color settings (in Text Style, Drop Shadow / Outline and the rack's Colors) open the
  color screen: the - and + buttons (or tap the bar), Copy color, Paste color.
- Section order: reorder the sections with the arrows, and switch "Hide lower sections
  in folders" on or off.
- Wallpaper: enable, select image, fit (Fit / Fill / Stretch / Original size),
  darken / lighten (-100% to +100%).
- Module Rack: Enabled, Modules, Side, Width, Edge sensitivity, Colors and Font settings.
  The modules are System (battery, frontlight, storage and used and total space, each
  switchable), Reading stats, Highlights and Vocabulary; it opens with a swipe inward from
  the chosen edge and closes with a tap outside it, a swipe back toward the edge, or Back.
  Swipe up or down to page through the cards.
- Extras: Build Mode, Settings access, Homescreen Presets, Module Rack presets and Refresh
  cover cache.
- The Settings menu also has Restart KOReader and Quit KOReader.
- Pull down from the top edge for KOReader's own top menu at any time. It also
  has Tools > ennUI, which opens the home screen.
- Optional: assign the action "ennUI: home screen" to a gesture.

## One-time tutorials
Toasts, each shown once, ever:
- Right after your first setup, a reminder of how to open Settings (the gear icon or the
  swipe up, whichever is chosen; the other one is shown the first time you switch to it).
- The first time you turn weather on, a reminder that tapping it refreshes it.

## About the file-browser flash
ennUI builds its screen the moment a book closes and reacts the instant
KOReader shows the file browser, when that signal is available, so the switch
back is close to instant on most setups. This is working within what a plugin
can do without changing how KOReader's own file browser gets shown, so it
isn't an absolute guarantee in every situation.

## Safety
- Errors while building or showing a screen leave the normal file browser in place.
- If the gear can't be built, the swipe up from the bottom edge opens Settings anyway.
- The loading splash (used only on the slower fallback path) closes itself
  after 5 seconds if nothing replaces it.
- If a start never finished drawing the home screen, the next start skips it once.
- To remove ennUI: delete the `ennui.koplugin` folder (and `settings/ennui.lua`).

## Known limits
- Very high outline thickness still means more paint work than none at all —
  it's linear in thickness, not free.
- White text will be invisible against the default blank background unless
  paired with an outline or a dark wallpaper.
- Covers can only be read from books KOReader can open and that contain a cover
  image. Opening a book to read its cover takes a moment on slower e-readers, which
  is why it happens in the background, once per book.
- Vertical covers fill all the height left on the screen when there are enough of them, so
  sections below the Book Cover module get squeezed (put it last in Section order, or lower
  the number or size of covers).
- A see-through rack panel is shaded in as many gray levels as the screen has; on a
  16-gray screen the blend is smooth in the framebuffer but shows in 16 steps.
- The menus (the gear menu and the preset actions list), the image chooser and KOReader's own
  entry box (used to type a number, a ZIP code or a name) are still KOReader's standard ones.
- The outline/drop shadow effects won't apply to a character your font draws
  as a picture-style glyph rather than a plain shape.

# v1.7 · 2026-10-28

## What's new in 1.7
- **Module Rack changes.** (The rack first appeared in 1.6: a panel that appears over the
  home screen from the left or right edge, full height and about half the screen wide,
  with the edge against the screen edge flush and the inside edge rounded.)
  - **System:** Battery and Storage are now one card. In its options, Battery,
    Frontlight, Storage and Used and total space can each be switched on or off. Racks
    set up in 1.6 carry over: a rack that had only one of the two keeps only that one.
  - **Highlights** now come from every highlight in every book you've opened, not just
    recent ones (the "Books to draw from" setting is gone). They're kept in a small index
    file (`cache/ennui_highlights.lua`) that is brought up to date in the background, a
    few books at a time, and only for books whose data changed, so the first run on a big
    library can take a little while and later runs are quick. One highlight is picked when
    you open the rack and nothing else changes it. **Tap** it to see the whole highlight
    (with your note and the book) in a pop-up. **Long-press** it to load a different one.
    This fixes taps on the card doing nothing in 1.6.
  - **Reading stats** are worked out at most once every 24 hours and kept; **long-press**
    the card to refresh them now. The card says when it was last updated, so the Today
    row can be out of date until then. The current book's progress is always read fresh.
  - **Font settings** (Module Rack > Font settings): a typeface and size for card titles,
    and a typeface and size for everything else, applying to every module. The big
    numbers are 1.9 times the body size and the small captions 0.85 times.
- **Smaller tap areas.** Plugin entries, the weather line, the page indicator and each
  cover now respond to taps only on the item itself plus about 8 pixels of invisible
  margin (covers: at most half the gap between them), not across the whole width of the
  screen. The alignment setting still decides where they sit.
- **Build Mode long press** now uses where each item really is on screen: long-pressing
  on the date, clock, weather, a plugin entry or a cover (or just beside it) opens that
  section's settings, and long-pressing empty space beside it does nothing. This should
  also fix long-pressing Recent books. If it still doesn't work, the log line "long press
  at ... isn't on any section" shows where the press landed.
- Everything else from 1.6 works as before: Refresh cover cache under Extras, Recent
  books wrapping like text, Hide lower sections in folders, padding from -1000 to +1000,
  and the color screen with its - and + buttons, Copy color and Paste color. Opacity is
  still gone.
- Version numbers use two digits (1.7).

# ennUI · 2026-10-04

**What's new in 1.0**
- Renamed throughout to **ennUI** (the capitalization you'll see everywhere
  it's displayed — toasts, menu titles, the plugin listing).
- The Plugin entries "Max entries per page" setting now reads
  **"Auto-fit to page"** instead of "No limit" when no cap is set.
- KOReader's top menu (Tools) now has a single **"ennUI"** entry, which takes
  you to the home screen. The separate "ennUI settings" entry is gone — swipe
  up from the bottom of the home screen for Settings, as in the last version.
