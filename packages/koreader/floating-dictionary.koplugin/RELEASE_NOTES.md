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
