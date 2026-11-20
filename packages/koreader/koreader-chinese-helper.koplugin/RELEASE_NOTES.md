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

# v2.14.0 · 2026-11-20

Simplified forms for traditional taps (#50)
- A character or word tapped in traditional characters (a page of a traditional book, or MOE's
  and the 成語典's text in a popup, now in MOE's own characters since 2.13.0) shows its
  simplified form on the head line, in bold, with the form as tapped beside it, small and grey,
  just like a simplified tap: 頭 in 頭髮花白 is **头** 頭 *tóu*, the word **头发** 頭髮 *tóufa*;
  發 in 發現 **发** 發, 東西 **东西** 東西.
- A character shows **one** simplified form, the one the word around it uses (乾 in 乾淨 →
  **干** 乾; 噁 in 噁心 → **恶** 噁), else its head line's reading's (乾 on its own, read gān → **干** 乾).
  Nothing is added where the form is the same in both scripts (乾 in 乾隆, 著 in 著名, 人民).
- Applies to every block with a head line: CC-CEDICT's, the fallback dictionaries', MOE Always
  blocks, idiom blocks and nested popups. Simplified taps are unchanged (checked on 18,090
  common simplified words). A fallback row with an empty or other-length simplified form, or
  one outside the BMP that would draw as a box, adds nothing.
- Same setting, **Show traditional forms**; off, head lines are exactly as in 2.13.0.

# v2.13.0 · 2026-11-20

Dictionary text as each source writes it (#48)
- Each dictionary's text is now shown as its source writes it, by default: MOE 重編國語辭典 and
  the 成語典 (short lines and Origin & Usage) in MOE's traditional characters, Wiktionary's
  glosses with their Chinese as written (`original form of 廩／廪`), and CC-CEDICT's
  cross-references with both forms (`variant of 夠|够 gòu`, `used in 鞦韆|秋千 qiūqiān`).
- **New setting, Dictionary text** (Popup → Dictionaries): **Original** (default) or
  **Simplified**, which gives exactly the text of 2.12.0 (`variant of 够 gòu`). It applies from
  the next popup, to every block, MOE Always blocks, idiom short lines, the Origin & Usage view
  and nested popups. Head lines are unchanged (**头发** 頭髮), and so are the dictionaries that
  are simplified or English already (Xinhua, Moegirlpedia, CBDB, Wikipedia titles).
- Both versions are stored; nothing is converted on the device. **Rebuild your MOE and 成語典
  files** (`tools/build_optional.py --only moe,idioms --force`, then copy them over): files
  built before 2.13.0 hold one version, which the popup shows whatever the setting, and
  **Status** says so. `--traditional` is gone from the build scripts.
- Sizes: the release database 36.3 → 37.8 MB (the zip 17.4 → 17.6 MB); the MOE file 28.2 →
  45.2 MB, the 成語典 file 21.7 → 36.3 MB.
- MOE's popup label is now **國語辭典** (was MOE); the menu and Status still say MOE 重編國語辭典.
- A self-referring "variant of" sense is dropped in either form (`variant of 個|个 gè` on 个).

# v2.12.0 · 2026-11-20

Traditional forms on the head lines (#47)
- Each popup entry's head line shows the word's traditional form beside it, in the same
  typeface, smaller (0.8×) and grey, when it differs: **头发** 頭髮, **中国** 中國; nothing for
  人民. A word shows the one form its entry gives (发现 發現, 干净 乾淨). A single character with
  several shows them all, "/"-joined, the one the word around it uses first (发 in 头发:
  髮/發; 干 in 干净: 乾/干/幹), the character itself included when it is one of them.
- Applies to every block: CC-CEDICT's, the fallback dictionaries', MOE Always blocks and
  nested popups. A Wiktionary "traditional" form of another length (a longer wording, another
  word) is not shown. A book in traditional characters adds nothing. The entries' text and the
  components block are unchanged.
- **New setting, Show traditional forms** (on by default), after Show character frequency rank.

# v2.11.1 · 2026-11-19

Frequency ranks labels (#45, #46)
- The bundled option is now **Bundled: web, books, news, subtitles**, and its help names all of
  wordfreq's sources for Chinese: web pages, Google Books, news, film and TV subtitles,
  Wikipedia, Twitter and Jieba's wordlist (#45).
- With From my books on, the 字频 line shows just your rank (**字频 3,504**, or **5,700+** past
  your file's exact ranks), without "(my books)". A character not in your books still says
  **(bundled)**, since that rank is on a different scale (#46).
