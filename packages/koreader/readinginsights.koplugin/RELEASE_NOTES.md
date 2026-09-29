# v6.10.4

**Changed**
Switched reading time and read% rows on Book progress view - the progress bar now under te reading %.

# v6.10.3

**Fixed**
- Book stats popup: 
  - in the "Next 2 chapters" pages cell, the short
  page-count unit (e.g. "o.", "p.") no longer sits lower than and
  closer to the number than in the rest of the popup — it's now
  vertically centered with the same spacing used everywhere else.
  - pages cell now shows the
  full "page"/"pages" word whenever it fits, same as the regular
  (non-split) pages view, and only abbreviates when the translated
  word is too long for the available space.

# v6.10.2

**Fixed**
- Book progress popup: the "This chapter / Next chapter" pages view now correctly shows both of the next two chapters' page counts when "Next chapters shown" is set to 2 (Settings > Advanced settings > Book progress popup). Previously it silently showed only one chapter's page count in that view, even though the setting was already combining both chapters correctly in the reading-time view.
- Added short, single-line page-count abbreviations (e.g. "p.", "o.", "S.", "стор.", "pág.", "页") for all bundled languages so the two-chapter page counts fit side by side without overflowing.

# v6.10.1

**Changed**

Font picker changed from checkbox to radio button

# v6.10.0

**New**

The font picker now shows how the fonts looks
