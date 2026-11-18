# v2.7.0 · 2026-11-18

Every occurrence gets pinyin (#28)
- **A character that gets pinyin now gets it at every occurrence on the page**, not just the
  first, each in the reading it has there: rare characters, unusual readings in special words,
  the uncertain pair (xíng/háng) and remind-me readings alike. A reading marked known is bare
  everywhere, so each reading is now all or nothing per page; marking or clearing one from the
  popup changes every occurrence at once.
- Crowded lines drop pinyin about as rarely as before (on four sample books, roughly 1% of
  annotations at most, the most common characters first), and nothing overlaps.

# v2.6.0 · 2026-11-18

Known and remind-me readings (#26)
- **A button at the right of the popup's title bar marks the tapped character's reading**:
  **I know tāo** stops that reading from ever getting pinyin (any threshold, every book), and
  **Remind me: shū** makes a reading that wouldn't be drawn always get pinyin, once per page.
  Only that reading is affected: 刨 *bào* known leaves 刨 *páo* annotated. Marked, the button
  reads **Known tāo ✓** or **Reminding shū ✓**; a tap clears it. The page under the popup
  changes at once. An uncertain pair (xíng/háng) gets a button per reading and is hidden only
  when both are known. Nested popups have no buttons.
- **Known & remind-me readings** in the menu shows the counts, lists the marks (a tap clears
  one) and has **Clear all marks**, which asks first.
- Marks are kept by simplified form in `koreader/settings/chinesehelper_marks.lua`, which
  survives plugin updates. It is written only when a mark changes, atomically; an unreadable
  file is renamed aside, never overwritten.

# v2.5.3 · 2026-11-18

- **MOE for single characters defaults to fallback again** (#24): out of the box, a
  single-character popup shows MOE's entry only for a character CC-CEDICT lacks, in full. Set
  **MOE for single characters** to **always** (Dictionaries menu) to keep 2.5.0's MOE entry
  under CC-CEDICT's for every character, collapsed as before. A mode already chosen in the menu
  is kept; only the default changes.

# v2.5.2 · 2026-11-16


- **Words with no definition from any source are no longer listed in the popup.** A word known
  only from pypinyin's segmentation (不畅 in 受阻不畅) used to show its pinyin and "no definition
  in CC-CEDICT"; it is now left out, also when it is the word that decided the tapped
  character's reading (that character's own entry already shows the reading). Words with a
  fallback entry or a note still appear.

# v2.5.1 · 2026-11-16

- **A collapsed MOE entry ends in "[Tap to show more]"**, small and grey, right after its last
  shown line, instead of an "…" that did nothing when tapped. Tapping it, or the space after it,
  expands the entry; expanded, it ends in **[Tap to show less]**. The label line is plain "MOE"
  again, with no "show all" and no tap action. The characters before the marker still open
  nested popups.
