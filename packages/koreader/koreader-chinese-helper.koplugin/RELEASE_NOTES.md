# v2.19.3 · 2026-11-22

Neutral tones: the remaining Wiktionary candidates
- 25 more words take the neutral tone where CC-CEDICT gave a full tone: 这里 zhèli, 因为 yīnwei,
  意识 yìshi, 下面 xiàmian, 前面 qiánmian, 下去 xiàqu, 气氛 qìfen, 住处 zhùchu, 神仙 shénxian,
  牢骚 láosao, 荒唐 huāngtang, 滑稽 huáji, 孝顺 xiàoshun, 随和 suíhe, 黄瓜 huánggua, 斧头 fǔtou,
  干粮 gānliang, 围裙 wéiqun, 翻腾 fānteng, 饭量 fànliang and 阵势 zhènshi; also 把头 bǎtou,
  套近乎 tàojìnhu, 严紧 yánjin and 坷垃 kēla. Each has the 现代汉语词典 dot, or a 轻声 note, on a
  dictionary page or a page quoting 现汉. 下麵 "to boil noodles" keeps xiàmiàn.
- These are the 540 candidates whose neutral reading is not Wiktionary's main one, looked up with
  Claude Haiku and web search ($11.46). Not approved: 来往, 编辑, 枪手 and 烧纸, whose neutral
  reading belongs to another sense, and 父亲, 道行, 做学问 and 出落, whose only evidence was a
  Q&A site, Baidu Baike or a blog. No character's default reading changes.

# v2.19.2 · 2026-11-21

狗狗 is gǒugōu again (#64)
- 2.19.1 changed 狗狗 to gǒugou on a single Zhihu note. It now reads gǒugōu again, as in
  CC-CEDICT, and the lookup script won't approve it again.

# v2.19.1 · 2026-11-21

Neutral tones checked against Baidu Hanyu, and ü in cross-references (#63, #64)
- 外面 wàimian, 进去 jìnqu, 摇晃 yáohuang, 风水 fēngshui and 狗狗 gǒugou now take the neutral
  tone, where CC-CEDICT gave a full tone. The first four have the 现代汉语词典 dot in Baidu Hanyu,
  and 狗狗 has a written 轻声 note. Words that have the dot in only one of their senses keep
  CC-CEDICT's reading: 大大 "greatly" / dà·da "uncle", 过年, 憋屈, 隔断 and 小月. No character's
  default reading changes.
- The other 224 main-reading candidates were looked up too, through Baidu Hanyu's JSON or,
  after Baidu's captcha, Claude Haiku with web search. They had no evidence or a full tone,
  so they keep CC-CEDICT's reading. The evidence is in docs/neutral-tone-evidence.tsv.
- Some CC-CEDICT references spell ü as "u : ". They now show it correctly: "see 吕梁市
  Lǚliáng Shì" instead of "Lu:'liáng Shì", and the same in 律所, 功放, 女孩儿 and about 45
  other entries.

# v2.19.0 · 2026-11-21

Tap a cross-reference to open its word (#62)
- In CC-CEDICT's text, a word given with its pinyin can now be tapped: the 贤慧 in "variant of
  賢慧|贤慧 xiánhuì", 东西 in "see 东西 dōngxi", 家伙 in "used in 傢伙|家伙 jiāhuo", 个 in "CL: 個|个
  gè", 惠顾 in "(as in 惠顧|惠顾 huìgù)", and the word leading a variant's definition line ("贤慧:
  ..."). One tap, on any of its characters, either form of a traditional|simplified pair, or its
  pinyin, opens a popup for the whole word, titled with it, with its entry first and the reading
  the reference gives first.
- Taps anywhere else in CC-CEDICT's text still do nothing, and the Chinese dictionaries' text
  works as before.

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
