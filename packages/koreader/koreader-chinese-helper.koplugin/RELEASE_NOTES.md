# v2.8.0 · 2026-11-18


Learner mode (#25)
- **Which characters → All characters (learner mode)** puts pinyin above every Chinese character
  on the page, repeats included. With **I know …** in the popup (2.6.0) a beginner switches each
  reading off as they learn it, and the page thins out. Two more levels sit between that and the
  old lowest, 1,500: **outside the 500** and **outside the 1,000 most common**.
- **The commonest function words no longer show two readings**: 的 *de*, 了 *le*, 着 *zhe*, 这
  *zhè*, 么 *me*, 呢 *ne*, 个 *gè*, 都 *dōu*, 还 *hái* and 与 *yǔ* are hand-checked defaults
  (their other readings come from words: 的确, 了解, 睡着, 首都, 还清, 参与). Before, the
  learned data put them in the uncertain list (的 *de/dì*, 了 *le/liǎo*), which never showed at
  the old levels but would have put 25–35 pairs on a page of 鲁迅 in learner mode; now about
  one character in a hundred keeps a pair there (得 *de/děi*, 过 *guò/guo*, 长). The popup marks
  them the same way. Characters with a single hand-checked reading are now never listed as
  uncertain, so the particles 哩 *li*, 咯 *lo* and 啦 *la* lose their pairs too (哩 showed *lǐ/li*
  above every 哩 in 平凡的世界). 着 in 生活无着 is now drawn *zhuó*, in bold, as an unusual
  reading. Nothing else changes at the other levels.
- No pinyin is dropped on crowded lines in learner mode on the sample book's pages (at 35% and
  40% size). On a Boox Go 7 a page takes a median 51.5 ms to prepare in learner mode, against
  30 ms at the default level.
- README: a **Learner mode** section, learner screenshots in the top grid, and the popup's
  **I know …** button.

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
