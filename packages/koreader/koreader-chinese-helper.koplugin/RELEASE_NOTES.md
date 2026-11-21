# v2.18.0 · 2026-11-21

Cross-reference-only CC-CEDICT entries show their target's definitions (#61)
- An entry whose only sense is a cross-reference now shows what it means: 贤惠 still reads
  "variant of 賢慧|贤慧 xiánhuì", and below it "贤慧: (of a wife) wise and kind; perfect in her
  traditional roles". The same for 7,213 entries: "variant of" in all its forms (old, erhua,
  archaic, ...), "see" and "same as". The borrowed line follows the tapped form (賢慧: when
  賢惠 was tapped) and the Dictionary text setting; a chain of references (利是 → 利事 → 红包) ends
  on the word with the definitions, its pinyin shown.
- "used in", "abbr. for" and "see also" entries are unchanged, as are entries whose references
  lead to several different words (北海: see 北海公园, see 北海市). The build prints the counts.
- The database grows by 1.5 MB (44.6 MB).

# v2.17.2 · 2026-11-21

Neutral tones: the 普通话水平测试 must-read list (#60)
- 42 more words now read with their standard neutral syllable, on the page and in the popup's
  word line: 37 from the 普通话水平测试 must-read neutral-tone list where CC-CEDICT had a full
  tone (灯笼 *dēnglong*, 队伍 *duìwu*, 打算 *dǎsuan*, 老婆 *lǎopo*, 疟疾 *nüèji*, ...), and 5 rare-
  character words with dictionary evidence found by web lookup (喜鹊 *xǐque*, 鹌鹑 *ānchun*, 荸荠
  *bíqi*, 蹊跷 *qīqiao*, 腌臜 *āza*). The other 503 words on the list already read correctly.
- A character's own default reading is unchanged (笼 stays *lóng*).
- `docs/neutral-tone-candidates.tsv` and `docs/neutral-tone-evidence.tsv` list every candidate
  and the evidence; the scripts that build them are in `tools/`.

# v2.17.1 · 2026-11-21

Neutral tones CC-CEDICT writes as full tones (#60)
- 喷嚏 and 打喷嚏 now read *pēnti* / *dǎpēnti*, as they are said in Standard Mandarin: the
  pinyin drawn above 嚏 is *ti* (it was *tì*), and the popup's word line reads *pēnti*. 嚏's own
  entry stays *tì*.
- New hand-edited list, `data/neutral_tone_overrides.tsv`, for words CC-CEDICT gives full tones
  that are usually read with a neutral syllable. The build puts the neutral tone into CC-CEDICT's
  line, so the existing neutral-tone rule draws it. The README says how to add a word. More words
  will follow.

# v2.17.0 · 2026-11-21


Popup labels: the source label on its own row, CC-CEDICT always labelled (#59)
- The small grey lines above an entry are now two rows: first the tapped character's 字频 rank
  (and **spoken here**, when shown), then the entry's source label on a row of its own. A label
  and 字频 no longer share a line (it read `文言 · 字频 16`, as if 字频 belonged to the
  dictionary).
- CC-CEDICT entries are now always labelled **CEDICT**, with Classical mode on or off, so the
  文言 entry and CC-CEDICT's are easy to tell apart.
- **Source labels** now offers **All entries** (default) and **None**; "Other dictionaries only"
  is gone, and a saved "other dictionaries only" setting reads as All entries.
- Menu help, README text and screenshots updated.

# v2.16.0 · 2026-11-21


Classical mode: the Classical entry first, in full (#56)
- With Classical mode on, the tapped character's 文言 entry is now the first entry in the popup,
  above its CC-CEDICT entry, and shown in full: every sense, no [Tap to show more]. The 字频 rank
  moves up with it, onto its label line. Everything else follows below, in the same order as with
  the mode off. A simplified character with two Classical entries (发: 發, 髮) shows both on top.
  Popups opened from a popup's text do the same.
- The title-bar button now reads **文言 Mode** (on: **文言 Mode ✓**). The entry's own source label
  stays 文言.
- With the mode off, or for a character with no Classical entry (吗), the popup is unchanged.
- README text, menu help and screenshots updated for the new order and label.

Night mode: no grey text in the popup (#57)
- In KOReader's night mode, the popup's small grey text (source labels, 字频, spoken here, note
  labels, [Tap to show more]/[Tap to show less]) is drawn in the normal text colour, in every
  popup and in Origin & Usage: inverted grey was hard to read on the Boox's e-ink. Day mode and
  the button separators are unchanged.
