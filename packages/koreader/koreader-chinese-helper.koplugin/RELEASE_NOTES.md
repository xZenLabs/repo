# v2.9.1 · 2026-11-18


No punctuation lines in Translate & Analyze (#31)
- **Translate & Analyze no longer gives punctuation marks a line of their own.** The learner
  prompt (2.8.1) said to skip punctuation, but gemini-3.5-flash-lite listed every mark anyway
  (often with an empty meaning: "，(,):"), 4–7 lines per reply in three takes out of three. The
  rule is now said outright, in the system prompt too, and the example ends in a ！ that gets no
  line. Three takes with the new prompt: no punctuation lines, 15–18 entries.
- The README's Translate & Analyze screenshot is retaken with the learner reply, and its alt text
  rewritten.

# v2.9.0 · 2026-11-18

Larger line of text at the top of the popup (#32)
- **The line of text from the page at the top of the popup is now drawn at the Chinese text
  size** (130% of the popup text by default) instead of the popup text size, so it reads like
  the page and follows **Chinese text size**. The tapped character stays bold and underlined.
  On a Boox Go 7 the 孔乙己 line (31 characters) still fits whole at 130%; at 175% the popup
  shows 29 characters of it.
- The same goes for the line under the title of **KOReader's dictionary popup** opened from a
  word button: it is drawn at the Chinese text size of that popup's text.
- The menu help for **Chinese text size** and **Show the text around the character in the popup**,
  and the README, say so.

# v2.8.2 · 2026-11-18

Menu and description wording (#29)
- The pinyin toggle is now **Show pinyin** (was "Show pinyin above rare characters"): with
  **Which characters → All characters (learner mode)** it puts pinyin on every character, and
  **Which characters** already says which ones. The setting itself is unchanged.
- The **Dictionaries** help names MOE's items as they appear in the menu, **MOE for single
  characters** and **MOE for words**.
- The plugin description (KOReader's plugin manager) covers learner mode and known / remind-me
  readings.

# v2.8.1 · 2026-11-18

Translate & Analyze for learners (#30)
- **The popup's Translate & Analyze button now explains every word**, in order, for someone
  learning Chinese: a natural English translation, then one line per word with its characters,
  tone-marked pinyin and its meaning in this sentence, small words included (的, 了, 吧,
  measure words), and a short note on how the sentence fits together when its structure would
  surprise an English speaker. Grammar is described in plain words ("得 between a verb and a
  result means 'able to'"), not named ("potential complement"). Before, the prompt was written
  for advanced readers and skipped words they would know on sight.
- On a Boox Go 7 a 69-character sentence from 阿Q正传 gets its whole reply (about five pages of
  KOAssistant's viewer) within the 2000-token limit.

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
