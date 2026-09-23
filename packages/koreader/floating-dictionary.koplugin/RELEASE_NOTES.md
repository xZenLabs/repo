# v6.2.0

**WHAT'S NEW**

- New "Kindle" popup style (Appearance > Popup style), alongside Classic and Kobo
- Full-width panel docked to the screen edge, with square corners and a single top rule. This style always uses the "screen edge" position, regardless of your saved position setting.
- The headword is shown in bold, with the phonetic pronunciation pulled out of the dictionary entry and placed on the same line.
- Definition body in italics, with the dictionary source cited at the bottom under a hairline rule.
- Your buttons appear as a tab row ("Dictionary | Wikipedia | Translate | ..."), in the order you configured. The active tab is underlined. Tab
- labels are never truncated: if they don't fit, the spacing shrinks first, then the font size. Only the previous/next arrows stay in the footer.
- New "Other plugins" submenu (replaces the single "Show buttons from other dictionary plugins" toggle). It has a master on/off switch and lists every button registered by other dictionary plugins. For each one you can move it up/down, show/hide it, and set its button text and icon.
- Small selection menu overhaul:
- The limit goes from 3 to 5 buttons, enforced both in settings and when the menu is rendered.
- Buttons now come from three sources: the text buttons from "Buttons shown in preview" (Highlight, Wikipedia, Translate, Search, Save for review...), Add Note, and buttons from other plugins.
- Buttons from other plugins get their own Button Text for the small menu, independent from the one used in the preview.
- The small menu now runs buttons from other plugins correctly.
- Wikipedia and Translate now check your connection first. If Wi-Fi is off and you decline the "connect?" prompt, the card stays open instead of closing and leaving the word selected with nothing to show. This applies to the footer, the Kindle tabs and the small menu.

**IMPROVEMENTS AND FIXES**

- Custom Button Text is no longer truncated (for example "Tradu..."). The cause was a faulty width expression that capped the label at about 80px. Buttons now size to their text, and in the justified footer each button gets at least the width its label needs.
- The small menu card is no longer limited to 62% of the screen width, so long labels show in full.
- "Buttons shown in preview" now lists only text buttons. Nav arrows and other plugins' buttons are managed in their own places.
- Tapping a button from another plugin closes the small menu and cards, runs the plugin's action, and clears the original word's highlight once that plugin's window closes.
- Looking up a word from inside an open definition now keeps the card position defined by your settings.
- Small menu: it now resolves its own action ids correctly. The previous code could not, which could stop the menu from appearing.

**REMOVED**

- Display mode (Personal / Minimal / Full / Language learner), including its menu entry and its effect on the footer. Footer visibility is now controlled only by "Buttons shown in preview" and "Other plugins". The old floatingdictionary_display_mode setting is simply ignored.

# v6.1.1

Fixed:
A crash triggered when using the small selection menu (the quick menu shown when you select text). A misreferenced variable in getSmallMenuButtonIds/showFloatingActionMenuForSelection caused KOReader to crash on that action. No changes to dictionaries, fonts, or settings.

# v6.1.0

**New**
Buttons added by other dictionary plugins ([Assistant](https://github.com/omer-faruq/assistant.koplugin), etc.) now get the same customization as the built-in buttons: order, show/hide, custom text, and custom icon, all from `Buttons shown in preview`. Closes #17.

**Fixed**
Tapping Wikipedia and closing its window no longer leaves the highlight stuck in the text or triggers a stray new dictionary popup. Closes #19.

# v6.0.0

**Fixed:**
- Very long press menu now works with Smart Highlight on multi-word selections (issue #16). Before, selecting 2+ words with Smart Highlight enabled always created a highlight, so the very long press never opened the menu. Now:
- Normal press: instant highlight (unchanged).
- Very long press (finger resting on the final selection for the long-hold time): KOReader's native highlight menu opens (Select, Search, Add note, other plugins' actions), the same behavior single words already had.
- The timing follows KOReader's own long-press interval (Settings → Taps and gestures).

**Important: manual install required this one time**

To get this version, delete the old floatingdictionary.koplugin folder from the plugins folder of KOReader on your e-reader, copy the new one there (extract floatingdictionary.koplugin.zip), and restart KOReader. This is only needed this once.

**Update from inside KOReader**

From now on you no longer need to copy files by hand. Go to Floating Dictionary → Check for updates. The plugin checks GitHub Releases, shows the release notes, downloads the new version and installs it in place. Then just restart KOReader (there's a "Restart now" button).
