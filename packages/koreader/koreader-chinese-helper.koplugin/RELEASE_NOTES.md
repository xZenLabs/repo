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

# v2.5.0 · 2026-11-16

MOE always shown for single characters (#11, #18)
- **With the optional MOE dictionary, every single-character popup shows MOE's entry under
  CC-CEDICT's**, even when CC-CEDICT has the character: 涓 gets 细流。/ 姓。/ 细缓的、细微的。/
  清洁的。/ 选择。 under "brook; to select". Placement: CC-CEDICT's entry (with the 字频 rank),
  then MOE's, then the components, then the words.
- **MOE's entry is collapsed to two lines** as drawn, ending in "…", with all its readings as
  one block (和's six). The grey label line reads **MOE · show all**; a tap there expands the
  entry in place (**show less** cuts it again), and the popup keeps its scroll position. The
  characters left visible can be tapped for a nested popup; the hidden ones can't. A new
  **Collapse long entries** setting picks 1, 2 or 3 lines, or never.
- MOE's readings follow CC-CEDICT's order (the likely reading first). A reading CC-CEDICT doesn't
  list for the character is marked **· not in CC-CEDICT** (和 *hàn*, 亡 *wú*, 不 *fǒu*); 1,432 of
  the 9,910 characters MOE shares with CC-CEDICT have one.
- **MOE for single characters** and **MOE for words** are each off / fallback / always (defaults:
  always, fallback). Fallback is 2.4.0's behaviour. The MOE switch overrides both, and existing
  settings carry over (MOE off stays off).
- **The menu's "Fallback dictionaries" is now "Dictionaries"**, with a new **Order** item
  (KOReader's sort widget) instead of the hand-edited `fallback_order` setting, which still
  holds the order. **Status** shows MOE's modes and whether its file is ready for Always.
- **Rebuild the MOE file for Always** (`tools/build_moe.py`): it now keeps the headwords
  CC-CEDICT has, as covered rows (11,871 character rows, 50,669 word rows). It grows from 17.0 MB
  to 28.2 MB. Its 90,501 fallback rows are unchanged. With an older file, Always works as
  Fallback, popups are identical to 2.4.0's, and Status says to rebuild. The plugin database
  is unchanged.
- **Readings are unchanged.** Covered rows never reach the fallback or reading path. MOE still
  never decides a reading: `tools/eval_readings.py` gives byte-identical output to 2.4.0's, with
  and without Wiktionary fallback (72/72 regression cases).
- One query to MOE's file per tap, as before. On the Boox Go 7, building the popup takes a median
  25 ms with MOE Always against 21.5 ms with Fallback (12 common characters, 2 rounds each).

# v2.4.0 · 2026-11-16


The character's frequency rank (#17)
- **Every popup shows the tapped character's frequency rank** on its own entry, in small grey
  text: `字频 4,270` is its rank among characters in modern written Chinese (wordfreq, the same
  ranking the pinyin threshold uses). Past 7,000 it reads `字频 7,000+`, since the data is too
  thin there for an exact rank, and `字频 unranked` for a character not in the list.
- It is on the character's own entry only, also in nested popups and for a character inside a
  word or chengyu. Word entries, components and fallback words never show one. When the entry's
  source label is shown too, both share one line (`CEDICT · 字频 4,270`).
- New setting **Show character frequency rank**, on by default, next to **Show character
  components**. No database change.

# v2.3.0 · 2026-11-16


Wiktionary readings: Standard Chinese only (#15)
- **Wiktionary entries never show regional Mandarin pronunciations** (搛菜 is *jiāncài*, not
  *jiǎncāi*). Dialect words without a Standard reading take their characters' readings when those
  are unambiguous, and otherwise show no pinyin. The regional qualifier in the gloss ("(dialectal
  Mandarin, Northern Wu)", "(Xi'an Mandarin)" …) stays.
- How: a Wiktionary pinyin sound counts only when its tags are on an allow-list and include a
  Standard marker (Standard-Chinese, Standard, Mainland-China or Taiwan), so Nanjing, Xi'an,
  Sichuanese, Beijing-dialect, Harbin, Wuhan and other regional romanizations, and any tag added
  later, are left out. 1,374 entries have only regional readings: 385 rows now take their
  characters' readings (every character with exactly one CC-CEDICT reading; 子 *zǐ / zi* counts
  as two) and 887 rows show the word and definition without pinyin. Only one row that already had
  a Standard reading changed (悠千 *yōuqianr*, Wiktionary's Standard erhua form). Rows without
  pinyin never decide a reading on the page.
- The build now counts rows whose pinyin gives a character a toned reading CC-CEDICT doesn't
  have: 1,025 → 891, the rest mostly literary or variant readings (善贾 *shànjià*, 渔父 *yúfǔ*).
  Page readings on the CPP test split are unchanged.

"Likely here" only with evidence (#16)
- **The tapped character's reading is marked "likely here" only when something in the text
  picked it**: a dictionary word or special word around it, a fallback dictionary's word, or a
  context rule. When nothing did (传 in a title cut by the line, …传稿》), the usual reading
  still comes first, but unlabelled, as the uncertainty pair already was.
- `tools/eval_readings.py` reports accuracy by what decided the reading, now in the README's
  Accuracy section: context rules are right 99.9% of the time (919 test examples), words 98.0%,
  the plain default 97.2%.
