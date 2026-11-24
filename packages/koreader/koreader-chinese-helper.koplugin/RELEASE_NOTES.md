# v2.25.0 · 2026-11-24

One popup on screen at a time (#82)
- A popup opened from another (a character tapped in a popup, or Origin & Usage) now takes its
  place instead of being drawn on top of it, so there is only ever one **Close** row on the
  screen. It is placed like the first popup, away from the character tapped on the page.
- **Close** (and the Back key) goes back one step: the popup below comes back as you left it,
  scrolled where it was, with its title-bar buttons and Translate row. A tap outside still
  closes them all.
- A nested popup's title shows the way you came: 崇 › 莞, cut from the left with … when it is
  too long.

Headwords that follow the text you tapped (#80)
- **Show traditional in headwords** is replaced by **Headwords**, with four choices:
  **Simplified • traditional** (the default, as before: **头发** • 頭髮 for any tap),
  **As written • other form** (the form the text uses first: **頭髮** • 头发 in a traditional
  book, **髮** • 发 for a single character), **As written only** (頭髮 in a traditional book,
  头发 in a simplified one) and **Simplified only**.
- It applies to every head line: the tapped character, the words around it, 文言 Mode and MOE
  entries, and popups opened from a popup.
- If you had turned **Show traditional in headwords** off, Headwords starts on Simplified only.
- Suggested by Generalhooha in #78.

Popup text size in 10% steps (#81)
- **Popup text size** now offers every 10% from 40 to 120% of the book's text size (50, 70, 90
  and 110% are new). The default stays 60%.
- Suggested by Generalhooha in #78.

Word choice by segmentation (#75)
- The word that decides a character's reading (the pinyin on the page and the popup's "likely
  here") now comes from the most probable split of the surrounding text into words, using every
  CC-CEDICT word's frequency, instead of the longest word through the character. 到了 is read
  dào le (not liǎo from 到了 "finally"), 手中的诏书 zhōng de (not zhòng dì from 中的 "hit the
  target"), 一个劲敌 yī ge jìngdí (not 一个劲).
- Checked on three books and the two samples with every character drawn: 3,122 readings change
  in about 560,000 characters; of 30 checked by hand, 25 are better, 4 the same and 1 worse
  (占梦). The regression set has no regressions.
- A learner-mode page (pinyin on every character) builds in about 56 ms on a Boox Go 7, 8 ms
  more than 2.24.0. The database grows from 53 to 56 MB.

# v2.24.0 · 2026-11-22


Headwords: simplified • traditional, at the same size (#73)
- Each entry's headword shows its traditional form after the simplified one, at the same size
  and separated by a dot: **头发** • 頭髮, **门** • 門. The simplified form is bold. Nothing is
  added when the two are the same (人, 大人).
- A single character lists only its other forms, not itself: 干 • 乾/幹/榦 (it used to list
  乾/干/幹). In a word, the form the word uses comes first: 发 • 髮/發 in 头发.
- Tapped in traditional characters, the simplified form still comes first: 頭髮 shows
  **头发** • 頭髮.
- The setting is renamed **Show traditional in headwords** (still on by default). Off, every
  headword is simplified only, including traditional taps.
- The head line is now a single line of text, so in night mode the traditional form uses the
  normal text colour.

# v2.23.0 · 2026-11-22

Words first: the words around the tapped character come above the character's own entry (#71, #68)
- A new popup setting, **Words first**, on by default: the words around the tapped character,
  longest first, now come first; the character's own entry, its MOE entry and its components
  follow them, together. Tap 发 in 头发 and 头发 is at the top.
- The 字频 rank and the spoken-tone note stay on the character's own entry. 文言 Mode's entries
  stay at the top, and the Chinese-language dictionaries' entries last. The buttons are unchanged.
- Turn it off in the popup settings (after **Show character components**) to have the character
  first, as before. It applies to popups opened from a popup too.
- Suggested by Generalhooha in #68.

# v2.22.0 · 2026-11-22

文言 Mode: evidence, not an AI's judgement, decides which senses are classical (#69)
- A sense stays in the 文言 entry if a dictionary marks it classical (Chinese Notes, Wiktionary,
  CC-CEDICT's own labels), or if MOE (重編國語辭典) gives the same sense with a quotation from a
  classical work written up to 1911. Vernacular novels, drama and anything after the Qing don't
  count. This replaces 2.21.0's AI check, which wrongly left out about 1 in 6 of the senses it
  removed.
- Back in: 邦交 *diplomatic relations* (《周禮》), 外侮 *foreign aggression* (《左傳》), 先行 *to
  proceed in advance* (《漢書》), and about 6,700 other senses. Still out: 就 *then*, 要 *need
  to*, 的 *of*.
- Left to the CC-CEDICT entry below: shared senses MOE quotes no classical text for, often a
  character's plainest one (一 *one*, 人 *person*, 有 *to have*, 是 *to be*). About 6,400 senses
  leave the 文言 entry.
- On 128 judged words from classical texts, the 文言 entry has the needed sense 91% of the time
  (95% in 2.21.0), first 65% (61%), in its first two 73% (73%); the whole popup still 95%.
- MOE's text is not bundled: only the yes/no decision is. The database grows by 0.5 MB, to 53.0 MB.

# v2.21.0 · 2026-11-22

文言 Mode: complete, purely classical entries, for characters and words (#67)
- The 文言 entry now lists every classical sense the sources give, numbered, commonest first, and
  always in full (no more caps of 8, 6 or 5). Senses that exist only in modern Chinese are left
  out: 的 keeps *target; bull's-eye*, not the structural particle; 就 keeps *to approach*, not
  *then*; 要 drops *need to*.
- Words get 文言 entries too: 26,093 words, from Chinese Notes, Wiktionary and CC-CEDICT
  (賤人 *a lowly person*, 北面 *to face north as a subject*, 所以 *that by which*). In 文言 Mode
  they follow the tapped character's entry, above everything else.
- Long entries: the commonest function characters run to 15–30 senses (之, 為, 將), and the popup
  scrolls to the rest.
- How it's built: Claude Haiku merged, ordered and marked each headword's senses; Claude Sonnet
  checked again the senses that came only from CC-CEDICT and left out 3,103 as modern-only. On
  128 judged words from classical texts, the entry has the needed sense 95% of the time (93%
  before), in its first two senses 73% (77%), and the whole popup 95%.
- The database grows by 6.1 MB, to 52.5 MB.
