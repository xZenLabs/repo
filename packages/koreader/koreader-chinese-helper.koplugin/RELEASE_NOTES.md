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

# v2.15.0 · 2026-11-20

Classical mode (#53) and the Classical dictionary (#55)
- A new **文言** button in the popup's title bar, left of the reading-mark button, turns
  Classical mode on (**文言 ✓**). It stays on for later popups, in every book and after a
  restart, until tapped again; it is also **Classical mode** in Popup → Dictionaries (off by
  default). Popups opened from a popup's text follow it but have no button.
- With it on, the popup shows the tapped character's **Classical dictionary** entry right under
  its CC-CEDICT entry, labelled 文言: up to five senses classical texts use and modern Chinese
  mostly doesn't (之 *him; her; it*, 說 = 悅 *pleased*), cut to two lines with
  [Tap to show more]. A simplified character shows the traditional form its word uses (发 in 头发
  → 髮); a variant form (説) shows its standard form's entry (說).
- The dictionary covers 21,292 characters and 184 variant forms. It was condensed once by Claude
  Haiku (`tools/build_classical.py`, Batch API, $1.37) from Chinese Notes' *Literary Chinese*
  senses (CC BY-SA 3.0), English Wiktionary (CC BY-SA 4.0) and, for characters outside the 3,000
  most common, Unihan (Unicode License v3); the result is CC BY-SA 4.0. Senses that cite no
  source line, or that only restate a reading, are dropped. On the research note's sample,
  CC-CEDICT alone had the needed sense 84% of the time, with the Classical dictionary under it
  95%.
- The database grows from 37.8 MB to 43.1 MB (the zip by 1.5 MB).
- README screenshots retaken with the 文言 button.

# v2.14.3 · 2026-11-20


Neutral tones the traditional form can't decide (#52)
- 处 in 好处 is now marked **chù** "likely here" and listed first (was chǔ, the character's
  default). The same goes for 坏处, 害处 and 难处 (chù), 答应, 照应 and 满口答应 (yìng),
  裁缝 (féng), 思量 and 掂量 (liáng), 停当 (dàng), 大部分 (fèn), 松散 (sǎn) and
  哭丧(着)脸 (sāng), in simplified and traditional text.
- These come from a short hand-checked list, used only where #51's scan found that the
  traditional form can't decide and that MOE's citation tone differs. Each one is a reading MOE
  and pypinyin's phrase data agree on (难处: the neutral word nánchu, "difficulty").
  Taiwan readings (悄悄话 qiǎo, 连累 lèi) and 生分, where the sources disagree, are left out.
- Only the popup's marking changes; the pinyin drawn on the page is the same.

# v2.14.2 · 2026-11-20


Head line's second form in the text's shade (#54)
- The traditional form beside a headword (**观** 觀), and the form as tapped beside a
  traditional tap (**头** 頭), are now the same shade as the text, not grey. They are still
  smaller and not bold. The label line, 字频, the spoken-tone note and [Tap to show more] stay
  grey.
- README screenshots with a second form retaken.

# v2.14.1 · 2026-11-20

Neutral tones marked by the word's traditional form (#51)
- 发 in 头发 is now marked **fà** "likely here" and listed first (was fā, "to send out"). The
  word draws 发 neutral (tóufa), and two of 发's entries have those letters. The popup now
  picks the one whose traditional form the word uses (頭髮 → 髮 → fà), and falls back to the
  character's default reading only when that doesn't separate them (含糊's 糊: hú).
- A scan of every CC-CEDICT word with such a tie (`tools/scan_neutral_ties.py`: 323 ties on 76
  characters) found 6 changes, all for the better: 头发, 剪头发, 烫头发, 耳发 and 头发胡子一把抓 (fà), and
  跟斗 (dǒu, was dòu). The other 317 ties keep the default.
- Only the popup's marking changes; the pinyin drawn on the page is the same.
