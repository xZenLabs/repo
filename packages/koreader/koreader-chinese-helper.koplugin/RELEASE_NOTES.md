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

# v2.9.2 · 2026-11-19

Popup buttons outlined in night mode (#43)
- **In KOReader's night mode, the lines between the popup's bottom buttons are visible again.**
  KOReader draws them light grey (0xAA); night mode inverted that to a dark grey (0x55) on
  black, which the Boox's e-ink hardly shows, so the word buttons, Translate & analyze and
  Close read as loose text. In night mode they are now drawn so they come out light grey
  (0xAA) on black, as day mode's are on white. Day mode is unchanged (same pixels). The
  popup's other lines and grey text were already visible in night mode.

# v2.9.1 · 2026-11-18


No punctuation lines in Translate & Analyze (#31)
- **Translate & Analyze no longer gives punctuation marks a line of their own.** The learner
  prompt (2.8.1) said to skip punctuation, but gemini-3.5-flash-lite listed every mark anyway
  (often with an empty meaning: "，(,):"), 4–7 lines per reply in three takes out of three. The
  rule is now said outright, in the system prompt too, and the example ends in a ！ that gets no
  line. Three takes with the new prompt: no punctuation lines, 15–18 entries.
- The README's Translate & Analyze screenshot is retaken with the learner reply, and its alt text
  rewritten.
