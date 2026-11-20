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

# v2.11.0 · 2026-11-19

Your own frequency ranks (#42)
- **New setting, Frequency ranks**: **Bundled (modern Chinese)** (the default, as before) or
  **From my books**. On a computer, `tools/build_user_ranks.py` ranks characters by your own
  books (from `tools/fetch_books.py`, or `--epubs DIR`): by how many works a character appears
  in, then how often, so one novel's cast of names cannot make rare characters common. Volumes
  of one work and duplicate copies count once; traditional forms count as simplified, 〇 as 零.
  `--push` copies the file to `koreader/settings/chinesehelper_ranks.tsv` over USB.
- With From my books on, the ranks decide which characters get pinyin, the popup's 字频 line
  and which pinyin is dropped first on a crowded line. Characters not in your books keep their
  bundled rank. 字频 says which it shows, **(my books)** or **(bundled)**, and shows **N+**
  past the ranks the library can tell apart (the file's exact cut-off).
- Nothing about the data changes: which words are held in memory and everything the database
  build decided keep the bundled rank. The release ships no one's ranks; From my books is
  disabled until you have a file.
- `tools/compare_user_ranks.py` compares a rank file with the bundled ranks (crossings at a
  threshold, and page-sized passages run through the plugin's own code).

# v2.10.0 · 2026-11-19

Spoken tones for 一 and 不, on in learner mode (#37)
- **New setting, Spoken tones for 一 and 不** (In learner mode, the default; Always; Never). The
  pinyin shows the tones of speech, as beginners' textbooks do: 一个 *yí gè*, 一天 *yì tiān*,
  不是 *bú shì*, 是不是 *shì bu shì*, 看不见 *kàn bu jiàn*, 吃不了 *chī bu liǎo*, 看一看
  *kàn yi kàn*. 一 stays *yī* as a number or ordinal (第一, 十一, 一九九八, 一月, 统一, 之一,
  一等奖) and before punctuation; between two units it is a quantity again (一万一千 *yíwàn
  yìqiān*). A verb and complement no dictionary word confirms keeps *bù*.
- Known and remind-me marks stay on the dictionary reading (**I know bù** hides 不 in every
  tone). The popup's entries keep *yī* and *bù*; the character's own entry gets a grey
  **spoken here: bú**.
- Measured on 49 books: about 800 sampled changes judged in context by AI reviewers over six rounds; each rule 97–100%
  right on the final code. tools/measure_sandhi.py does the scan and the judging batches.
- The README's learner-mode shots are retaken.

Leftovers of the two retired plugins removed (#34)
- No visible change. The one-time copy of koreader-interlinear-pinyin's and
  koreader-chinese-popup's settings (from 1.0.0), the warning when either was still installed,
  and the Status line naming them are gone, along with their tests. Settings already copied
  stay as they are. Code comments no longer cite the two old repos (the WordGloss credits
  stay), and tools/plugin_runtime.py no longer runs an interlinear-pinyin 0.5.0 copy.
