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

# v2.20.0 · 2026-11-22

文言 Mode: the Classical dictionary rebuilt for the top of the popup (#65)
- The 文言 entry now lists a character's senses in order of how common they are in classical
  texts, and it includes the senses classical and modern Chinese share when they are among the
  commonest: 而 now opens with *and*, 于 (於) has *in; at*, *from*, *than* and *by*, and 陰 has
  *secretly*. Modern-only senses are left out.
- Up to eight senses for the 500 commonest characters, six for the next 2,500, five for the rest
  (five for every character before).
- CC-CEDICT's senses are now among the sources the entry is built from. A character with only
  modern senses still gets no entry.
- On 128 judged words from classical texts, the entry's first two senses have the needed one 77%
  of the time (57% before), the whole entry 93% (73%), and the whole popup 95% (unchanged).
- 21,191 characters (21,292 before; the ones dropped had only modern senses, such as 氟 and 乒).
  The database grows by 1.8 MB, to 46.4 MB.

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
