# koreader-chinese-helper

**Read real Chinese books on your e-reader. Tap any character to see the words it forms in this
sentence, the reading it has here, and what it is made of. Show pinyin above only the rare
characters, or above every one, and take it away one reading at a time as you learn.**

A [KOReader](https://github.com/koreader/koreader) plugin for e-ink readers. Chinese has no
spaces between words, so an ordinary dictionary lookup means long-pressing, dragging a selection
and guessing where the word ends. Here you tap once. The plugin reads the text on both sides of
the character, finds the dictionary words actually written there, and marks the reading the
character takes in this sentence: 行 is *háng* in 银行 but *xíng* in 行人 (see
[Readings](#readings)).

- **Starting out?** Turn on pinyin above **every character on the page**
  ([Learner mode](#learner-mode)) and read a real novel from the start. Tap a character whose
  reading you know, mark it known, and that reading goes bare everywhere, in every book, so the
  pinyin thins out as your reading grows.
- **Reading confidently?** Keep pinyin only for the rarest characters, at the level you choose.
  Chengyu come with their classical sources, a [文言 mode](#classical-mode) adds the senses
  classical texts use, and Taiwan's MOE dictionary can be read in Chinese by
  [tapping its text](#tapping-a-character-in-the-popup).

Useful from your first Chinese book to your hundredth. It works on any reflowable book (EPUB,
FB2, MOBI, TXT and the like) as soon as you open it: nothing to prepare, and the book file is
never modified.

KOReader 中文阅读插件：点一个字，即可看到它在本句中组成的词及其释义，并标出它在此处的读音；还可在字上方显示拼音，从只标生僻字到每个字都标（学习模式），学会一个读音点一下即可隐去，初学者和熟练读者都适用。

![The opening of 三国演义 第一回 on a Boox Go 7: the chapter title, then the popup on 密. At its top, the line 时有宦官曹节等弄权，窦武、陈蕃谋诛之，作事不密，反为所害，中涓自此愈横。 with 密 in bold and underlined; the title bar, 密 on the left and the buttons 文言 Mode and Remind me: mì on the right; then 字频 646 in small grey and, on the row below, the label CEDICT; 密 mì, "dense; close; … (bound form) secret; confidential …", "Mì: surname Mi"; its parts, labelled Wikt: 宓 mì still; silent → sound (same sound), 山 shān mountain → meaning; then 不密 bùmì "(literary) not well thought out; (literary) not secret", labelled Wikt; buttons 密 and 不密, then Translate & analyze the surrounding sentence [AI] on its own row, then Close at the bottom. Below the popup, the end of the paragraph's last line, 密，反为所害，中涓自此愈横。, with 密 underlined on the page](docs/main.png)

It has only been tested on a Boox Go 7, but it should work on any e-reader that runs KOReader:
Kobo, Kindle, PocketBook, and Android devices such as Boox.

<table>
<tr>
<td width="50%"><img src="docs/learner.png" alt="A paragraph of 阿Q正传 in learner mode: pinyin above every character, 那还是上午的事 nà hái shi shàng wǔ de shì through 观音娘娘座前的一个宣德炉 guān yīn niáng niang zuò qián de yí ge xuān dé lú"><br><a href="#learner-mode"><b>From beginner to advanced</b></a>: pinyin on every character in learner mode …</td>
<td width="50%"><img src="docs/learner-known.png" alt="The same paragraph after the 80 commonest readings on the page were marked known: about half the pinyin is gone; what is left is mostly the less common characters, such as 赵 zhào, 辫 biàn, 庵 ān, 栗凿 lì záo, and 是 shi in 还是, whose shì alone was marked known"><br>… switched off one reading at a time as you learn them: the same paragraph with the 80 commonest readings on the page <a href="#learner-mode">marked known</a></td>
</tr>
<tr>
<td><img src="docs/off-on.png" alt="The 临江仙 that opens 三国演义, pinyin off (top) and on (bottom): with it on, only 樵 qiáo and 渚 zhǔ get pinyin, the rest of the page stays clean"><br><a href="#usage"><b>Pinyin only above the hard characters</b></a>, at the level you choose (here the default: outside the 3,500 most common)</td>
<td><img src="docs/context.png" alt="Popup for 间 in 孔乙己's 虽然间或没有现钱: at the top the line 但他在我们店里，品行却比别人都好，就是从不拖欠；虽然间或没有现钱，… with 间 marked; the 文言 Mode and reading-mark buttons in the title bar; 字频 113, then the label CEDICT, then 间 間 jiàn · likely here, jiān listed after it; its parts 门 and 日 labelled MMAH; labelled CEDICT, 间或 間或 jiànhuò · decides 间's reading, occasionally; now and then"><br><a href="#the-popup"><b>The reading it has here</b></a>, and the word that decides it: 间 is <i>jiàn</i> in 间或</td>
</tr>
<tr>
<td><img src="docs/components.png" alt="Popup for 茴 in 孔乙己's 要一碟茴香豆: at the top the line 他不回答，对柜里说：“温两碗酒，要一碟茴香豆。” with 茴 marked; the 文言 Mode and reading-mark buttons in the title bar; 字频 4,633, then the label CEDICT, then 茴 huí (bound form) fennel; its parts, labelled Wikt: 艹 cǎo grass; plant (草字头) → meaning, 回 huí to go back → sound (same sound); then 茴香豆 and 茴香, each labelled CEDICT"><br><a href="#character-components"><b>What each character is made of</b></a>: 茴 is 艹 for the meaning and 回 <i>huí</i> for the sound</td>
<td><img src="docs/traditional.png" alt="Popup for 观 in 阿Q正传's 观音娘娘: at the top the line …而且又不见了观音娘娘座前的一个宣德炉。 with 观 marked; the 文言 Mode and reading-mark buttons in the title bar; 字频 407, then the label CEDICT, then 观 觀 guān · likely here (觀 smaller), with guàn and Guàn after it; traditional 觀: 雚 guàn (archaic) stork; heron → sound (same sound), 見 jiàn see → meaning, simplified: 雚 → 又; labelled CEDICT, 观音 觀音 Guānyīn · decides 观's reading"><br><a href="#character-components"><b>Parts the simplification hid</b></a>: 观 is read through 觀, 雚 <i>guàn</i> → sound</td>
</tr>
<tr>
<td><img src="docs/chengyu.png" alt="Popup for 也 in 孔乙己's 满口之乎者也: at the top the line 他对人说话，总是满口之乎者也，教人半懂不懂的。 with 也 marked; the 文言 Mode and reading-mark buttons in the title bar; then 字频 38 and the label CEDICT, 也 yě; its Wikt line pictogram (象形), 满口之乎者也 (滿口之乎者也 beside it) and 之乎者也, each labelled CEDICT, 之乎者也 with a Chinese line labelled 新华: 这四个字都是文言虚词，讽刺人说话喜欢咬文嚼字。也形容半文不白的话或文章。; a 成语 Origin &amp; Usage button"><br><a href="#chengyu"><b>Chengyu explained</b></a>: 之乎者也 with Xinhua's line (optional file) …</td>
<td><img src="docs/chengyu-2.png" alt="The Origin &amp; Usage view for 之乎者也 from 新华成语: 释义; 出处 宋·文莹《湘山野录》：“之乎者也，助得甚事？”; 例句 他对人说话，总是满口之乎者也，叫人半懂不懂的。"><br>… and its <a href="#chengyu"><b>Origin &amp; Usage</b></a> view: the classical source and an example from this same passage of 孔乙己</td>
</tr>
<tr>
<td><img src="docs/classical.png" alt="Popup for 之 in 三国演义's 窦武、陈蕃谋诛之: the line 时有宦官曹节等弄权，窦武、陈蕃谋诛之，作事不密，反为所害，中涓自此愈横。 with 之 marked; the title bar, 之 on the left and the buttons 文言 Mode ✓ and Remind me: zhī on the right; first 字频 69, then the label 文言 on a row of its own and the Classical entry, in full: 之, him; her; it; them (object pronoun in non-subject position), genitive or attributive marker (possession or modification), nominalizer or subordinate-clause particle in a subject-predicate construct, this; these; that, to go; to arrive; below it, labelled CEDICT, 之 zhī (possessive particle, literary equivalent of 的 de); him; her; it; then its parts, labelled Wikt: 止 zhǐ foot → meaning, 一 yī the beginning place → meaning"><br><a href="#classical-mode"><b>Classical mode</b></a>: one tap on 文言 Mode puts the senses classical texts use first, here 之 as <i>him; her; it; them</i> in 窦武、陈蕃谋诛之</td>
<td><img src="docs/nested.png" alt="Popup for 秋 in the 临江仙, its title bar with the buttons 文言 Mode and Remind me: qiū, and on top of it the popup for 歡, tapped in MOE's quotation of 〈琵琶行〉: its line at the top is 「今年歡笑復明年，秋月春風等閒度。」 with 歡 marked and no buttons in its title bar, then 字频 443 and the label CEDICT, 欢 歡 huān, its parts 雚 and 欠 labelled Wikt, 欢笑 歡笑 huānxiào labelled CEDICT, and the buttons 歡 and 歡笑, then Close at the bottom (no Translate in a popup opened from a popup)"><br><a href="#tapping-a-character-in-the-popup"><b>Read the dictionary by tapping</b></a>: 歡, tapped in MOE's quotation of 〈琵琶行〉, opens its own popup on top</td>
</tr>
<tr>
<td><img src="docs/labels.png" alt="Popup for 秋 in the 临江仙's 惯看秋月春风: at the top the line 白发渔樵江渚上，惯看秋月春风。 with 秋 marked; the 文言 Mode and reading-mark buttons in the title bar; 字频 1,442, then the label CEDICT on a row of its own, then 秋 秋/鞦 qiū (used in 鞦韆|秋千 qiūqiān); its parts 禾 and 火 labelled MMAH; 秋月 labelled Wikt; last, 秋月春风 秋月春風 labelled 國語辭典 with MOE's definition in its own traditional characters, in larger type, quoting 白居易's 〈琵琶行〉: 「今年歡笑復明年，秋月春風等閒度。」; a 成语 Origin &amp; Usage button"><br><a href="#fallback-dictionaries"><b>Several dictionaries, each labelled</b></a>: CC-CEDICT for 秋, Wiktionary for 秋月, and MOE (optional) for 秋月春风, in larger type</td>
<td><img src="docs/translate-result.png" alt="KOAssistant's Translate &amp; Analyze viewer, titled with the model gemini-3.5-flash-lite, its whole reply shown as its two pages, joined by a dashed line. Highlighted text: 孔乙己便涨红了脸，额上的青筋条条绽出，争辩道：“窃书不能算偷……窃书！ Translation: Kong Yiji flushed red right away, the veins on his forehead bulging out one by one, and he argued, &quot;Stealing books cannot be considered stealing... stealing books!&quot; Then one line per word, in bold characters with pinyin: 孔乙己 (Kǒng Yǐjǐ) Kong Yiji, the name of the character; 便 (biàn) right away, then; 涨红了脸 (zhǎng hóng le liǎn) flushed red in the face [涨 swell/flush + 红 red + 了 shows change + 脸 face]; 额 (é) forehead; 上 (shàng) on, placed after a noun; 的 (de) connects the forehead to the veins that belong to it; 青筋 (qīng jīn) blue veins; 条条 (tiáo tiáo) strip by strip, one by one, repeated to show multiple veins standing out; 绽出 (zhàn chū) burst out, bulge out; 争辩 (zhēng biàn) argue, debate; 道 (dào) say, used here to introduce spoken words; 窃书 (qiè shū) stealing books, literary, old-fashioned words [窃 steal secretly + 书 book]; 不能 (bù néng) cannot; 算 (suàn) count as; 偷 (tōu) steal, the everyday, common word for stealing, unlike the literary 窃 used earlier. Below, the viewer's buttons: Reply, Copy, Save to Note, Notebook, Pin, Close and others"><br><a href="#translating-the-sentence"><b>Translate &amp; Analyze the sentence</b></a> with KOAssistant: a translation and a plain-English, word-by-word breakdown of 孔乙己's 窃书不能算偷, down to why he says 窃 and not 偷 (your own AI provider, while Wi-Fi is on)</td>
</tr>
</table>

<details>
<summary>About these screenshots</summary>

All screenshots: a Boox Go 7 (landscape), the [sample book](#the-sample-book), default settings
(the learner ones: All characters, and 80 readings marked known in the second),
with every [optional dictionary](#optional-dictionaries) installed. `tools/make_screenshots.py`
takes them again; KOAssistant's response is taken separately, by name, and is not retaken by
default, because the AI's answer differs from run to run.

</details>

### Features

- **One tap, no selecting**: tap anywhere in the text (on a character, between lines, on
  punctuation) and the nearest character opens; taps outside the text turn pages and open menus
  as usual ([What a tap does](#what-a-tap-does)).
- **Only the words on the page**: tap 宛 in 很大宛如 and you get 宛, 大宛 and 宛如, longest first,
  so a sentence that could divide two ways shows both ([The popup](#the-popup)).
- **A reading for every character**, common ones included, right 97.5% of the time on the hard
  cases ([Readings](#readings), [Accuracy](#accuracy)).
- **Pinyin at any level**, from every character ([learner mode](#learner-mode)) through outside
  the 500, 1,000 … 7,000 most common; common characters in an unusual reading (单 in 单于) get
  pinyin too ([Unusual readings](#unusual-readings-of-common-characters)).
- **Mark readings known as you learn them**, with one tap in the popup: that reading goes bare
  everywhere, in every book ([Known and remind-me readings](#known-and-remind-me-readings)).
- **The sentence on one line** at the top of every popup, the character marked, and the
  character underlined on the page while the popup is open ([The popup](#the-popup)).
- **Classical Chinese**: the popup's 文言 Mode button adds a Classical dictionary's senses. On 128
  words from classical texts, CC-CEDICT alone had the needed sense 84% of the time; with the
  Classical dictionary added, 95% ([Classical mode](#classical-mode)).
- **Chinese definitions you can read**: tap any character in MOE's or an idiom dictionary's
  text and it opens its own popup on top
  ([Tapping a character in the popup](#tapping-a-character-in-the-popup)).
- **Translate** the whole sentence with KOAssistant and your own AI provider, or with KOReader's
  built-in translator when KOAssistant is not installed
  ([Translating the sentence](#translating-the-sentence)).
- **Pinyin and popup are separate switches**; nothing is prepared per book, the book file is
  never modified, and long-press and KOReader's own dictionary are untouched.

### Dictionaries

CC-CEDICT comes first; the others, the [fallback dictionaries](#fallback-dictionaries), give
entries for words it lacks. The rows are in the order the popup checks them (the default; the
menu's **Order** changes it). The MOE dictionary can also show its entry for every character
(or word) it has, under CC-CEDICT's, collapsed to two lines ([MOE Always](#moe-always)).

| Dictionary | Label | Entries added | | Mainly covers |
|---|---|---|---|---|
| CC-CEDICT | CEDICT | 125,000 | bundled | modern vocabulary, in English |
| Wiktionary | Wikt | 61,000 | bundled | historical and literary terms, chengyu, technical terms, some slang |
| CBDB office titles | CBDB | 2,900 | [optional](#optional-dictionaries) | Ming and Southern Ming office titles |
| MOE dictionary | 國語辭典 | 90,500 (of its 161,000) | [optional](#optional-dictionaries) | historical and literary vocabulary (in Chinese) |
| MOE idioms | 成语典 | 3,700\* | [optional](#optional-dictionaries) | chengyu, with source texts and stories (in Chinese) |
| Xinhua idioms | 新华 | 23,500\* | [optional](#optional-dictionaries) | chengyu and set phrases, with classical sources (in Chinese) |
| Wikipedia titles | WP | 39,000 | bundled | technology, engineering, military and history terms, and proper names (English article title) |
| Moegirlpedia slang | Moegirl | 350 | [optional](#optional-dictionaries) | internet slang (in Chinese) |
| Classical dictionary | 文言 | 21,292 characters | bundled, [Classical mode](#classical-mode) only | the senses of single characters in classical Chinese, condensed from Chinese Notes, Wiktionary and Unihan |

\* Chengyu CC-CEDICT lacks. Both files also add a Chinese line and an Origin & Usage view to chengyu the
other dictionaries have: MOE idioms covers 5,470 chengyu in all, Xinhua idioms 30,200
([Chengyu](#chengyu)).

Optional dictionaries are files you build yourself, because their licences do not allow this
project to distribute them: a few commands on a computer, then a copy to the e-reader
([Optional dictionaries](#optional-dictionaries)). Each dictionary's text is shown as its source
writes it (MOE in traditional characters), or in simplified characters if you prefer
([Dictionary text](#dictionary-text)).

Status: **2.15.0**, tested on a Boox Go 7 (Android, 300 dpi) with KOReader v2026.07.1.

## Install

1. Download `chinesehelper.koplugin.zip` from the
   [latest release](https://github.com/scartoon/koreader-chinese-helper/releases/latest) and unzip
   it. You get a `chinesehelper.koplugin` folder, which includes the database
   (`data/chinesehelper.sqlite`, 43.1 MB).
2. Copy that folder into KOReader's `plugins` folder:
   - **Android** (Boox and others): `/sdcard/koreader/plugins/`, which appears as
     `koreader/plugins` in the device's internal storage over USB. With adb:
     `adb push chinesehelper.koplugin /sdcard/koreader/plugins/`
   - Other devices: the `plugins` folder inside KOReader's own folder.
3. Restart KOReader.
4. Optional: [build the optional dictionaries](#optional-dictionaries). Their licences don't let
   this project share them, so you make them yourself on a computer; they add most of the
   Chinese-language explanations and chengyu sources (the MOE dictionary alone adds 90,500
   entries).

The folder must keep its name, `chinesehelper.koplugin`. The repository does not contain the
database; to install from a clone, [build it](#building-the-database) first.

## Usage

Open a book, then **Tools (🔧) → Chinese helper** (the entry may be on the second page of the
Tools menu). Settings apply to all books.

| Menu item | |
|---|---|
| Show pinyin | On / off (off when first installed); **Which characters** sets which ones get it |
| Tap characters for popup | On / off (on when first installed) |
| Which characters | **All characters (learner mode)**, or pinyin for characters outside the 500 / 1,000 / 1,500 / 2,500 / 3,500 / 5,000 / 7,000 most common (default 3,500). See [Learner mode](#learner-mode) |
| Frequency ranks | **Bundled: web, books, news, subtitles** (default) / **From my books**, once you have built your own file. See [Your own frequency ranks](#your-own-frequency-ranks) |
| Pinyin size | 35–55% of the book's text size (default 40%) |
| When the reading is uncertain | Show both readings (default) / show the most likely reading / don't annotate |
| Spoken tones for 一 and 不 | In learner mode (default) / always / never: 一个 *yí gè*, 不是 *bú shì* in the pinyin, as beginners' textbooks write them. See [Readings](#readings) |
| Mark unusual readings of common characters (names, historical terms) | On (default) / off. See [Unusual readings](#unusual-readings-of-common-characters) |
| Known & remind-me readings | The counts; **Show marks** lists them (a tap clears one), **Clear all marks** (asks first). See [Known and remind-me readings](#known-and-remind-me-readings) |
| Edge pass-through width | 0 mm (off) / 2.5 mm / 5 mm (default) / 7.5 mm / 10 mm. See [What a tap does](#what-a-tap-does) |
| Popup text size | 40 / 60 (default) / 80 / 100 / 120% of the book's text size |
| Chinese text size | 100 / 115 / 130 (default) / 150 / 175% of the popup text size, for the Chinese dictionaries' text (MOE, 成語典, Xinhua, Moegirlpedia) and the line of text at the top of the popup. See [Tapping a character in the popup](#tapping-a-character-in-the-popup) |
| Show character components | On (default) / off. See [Character components](#character-components) |
| Show character frequency rank | On (default) / off. The small grey 字频 line on the tapped character's entry |
| Show traditional forms | On (default) / off. A word's traditional form beside it on each head line, when it differs: **头发** 頭髮; tapped in traditional characters, the simplified form first: **头** 頭 |
| Show the text around the character in the popup | On (default) / off; drawn at the Chinese text size. See [The popup](#the-popup) |
| Underline the tapped character on the page | On (default) / off. See [The popup](#the-popup) |
| Try to match the book's font | On (default) / off: Chinese text in the popup in the book's font. See [The popup](#the-popup) |
| Dictionaries | A submenu: see the table below |
| Status | Version, data versions and load times, each fallback dictionary (version, entries, on or off, or not installed; MOE's modes and whether its file is ready for Always), and what the current page needed |

The **Dictionaries** submenu:

| Menu item | |
|---|---|
| Source labels | All entries (default) / none |
| Dictionary text | Original (default) / simplified. See [Dictionary text](#dictionary-text) |
| Classical mode | Off (default) / on; the same as the popup's 文言 Mode button. See [Classical mode](#classical-mode) |
| Order | The order of the dictionaries after CC-CEDICT |
| Collapse long entries | 1 / 2 (default) / 3 lines / never |
| Each dictionary | On / off, listed in that order (default: Wiktionary, CBDB office titles, MOE 重編國語辭典, MOE 成語典, Xinhua idioms, Wikipedia titles, Moegirlpedia slang). See [Fallback dictionaries](#fallback-dictionaries) |
| MOE for single characters | Under MOE's switch: off / fallback (default) / always. See [MOE Always](#moe-always) |
| MOE for words | Under MOE's switch: off / fallback (default) / always. See [MOE Always](#moe-always) |

### Learner mode

For beginners: pinyin above every Chinese character on the page, so you can read a real book
from the start, and the plugin's job shifts from looking words up to taking the pinyin away as
you learn.

1. Turn it on: **Tools (🔧) → Chinese helper → Show pinyin** on, then
   **Which characters → All characters (learner mode)**.
2. Read. Every character has its reading as the plugin resolves it in context (了 is *le* after a
   verb, *liǎo* in 了解; see [Readings](#readings)), repeats included. 一 and 不 get their spoken
   tones (一个 *yí gè*, 不是 *bú shì*); the popup still lists the dictionary's *yī* and *bù*.
3. When you're sure of a reading, tap the character and tap **I know …** at the right of the
   popup's title bar. That reading goes bare at once, at every occurrence, in every book. Its
   other readings keep their pinyin: knowing 还 *hái* leaves 还 *huán* in 还清 annotated.
4. For a reading you keep forgetting, the same button on a character without pinyin reads
   **Remind me: …**, which does the opposite: that reading always gets pinyin, at any level.

![The popup for 盘 in 阿Q正传 in learner mode: at the top the sentence 赵秀才消息灵，一知道革命党已在夜间进城，便将辫子盘在顶上，一早去拜访那历来也不相能的钱洋鬼子。 with 盘 marked; then the title bar, 盘 on the left and the buttons 文言 Mode and I know pán on the right; below it 字频 1,107, the label CEDICT and 盘 盤 pán with its senses](docs/mark-button.png)

Your marks are kept outside the plugin's folder, so updates and reinstalls keep them (see
[Known and remind-me readings](#known-and-remind-me-readings) for the file to back up). When the
page has thinned out enough, step up to a numeric level: **outside the 500 most common**, then
1,000 and on. Characters more common than the level go bare, the rest keep their pinyin, and your
known and remind-me marks still apply at every level.

On a Boox Go 7 a page with pinyin on every character takes about 50 ms to prepare (30 ms at the
default level; see [Speed](#speed)). A few characters keep two readings where nothing on the page
decides between them (得 *de/děi*, 长 *cháng/zhǎng*), about one in a hundred in 鲁迅's stories;
**When the reading is uncertain → Show the most likely reading** shows just the first.

### Your own frequency ranks

By default, "the 3,500 most common" means most common in modern written Chinese at large. If you mostly read novels or histories, a script ranks characters by your own books instead, so the characters that get pinyin are the ones that are rare in what you read.

<details>
<summary>How to build and use your own ranks</summary>

"Outside the 3,500 most common" means most common in modern written Chinese: the bundled ranks
are wordfreq's for Chinese, mixed from web pages, Google Books, news, film and TV subtitles,
Wikipedia, Twitter and Jieba's wordlist. If you mostly read novels or histories, you can rank
characters by your own books instead, so that the characters that get pinyin are the ones that
are rare in what you read. On a computer, with the e-reader connected over USB:

```sh
python3 tools/fetch_books.py               # copy your EPUBs' text into build/ (when your library changes)
python3 tools/build_user_ranks.py          # count it into build/user-ranks.tsv
python3 tools/build_user_ranks.py --push   # copy that file to the e-reader (adb)
```

(`build_user_ranks.py --epubs DIR` reads a folder of EPUBs on the computer instead, and needs
no e-reader; copy the file across by hand then.) Then choose **Frequency ranks → From my books**.
The file goes to `koreader/settings/chinesehelper_ranks.tsv`, next to the reading marks, so
plugin updates keep it; the menu item's help gives its date and how many books it counts.

- A character is ranked by **how many of your books** it appears in, then by how often, so one
  long novel's cast of names cannot make rare name characters "common". The volumes of one
  work, and the same text twice (a book on the device and again as a file on the computer, or
  inside a boxed set), count once.
- Characters that are not in your books keep their bundled rank.
- The ranks decide which characters get pinyin, the popup's 字频 line and which pinyin goes
  first when a line is crowded. The 字频 line then shows your rank, **字频 3,405**, or, for a
  character not in your books, the bundled one marked as such: **字频 6,500 (bundled)**. Past the ranks your library
  is big enough to tell apart, it shows **N+** (for 42 books, 5,700+).
- Nothing else changes: the plugin's data, and which words it loads, are the same either way.
- Your books stay on your computer, in `build/` (not committed); the file holds only characters
  and counts.

</details>

### What a tap does

Inside the text, every tap opens the popup for the nearest Chinese character, and the page never turns. Margins, blank space and lines with no Chinese still turn pages and open menus as usual, and an edge band keeps page turns reliable with small margins.

<details>
<summary>Exactly where a tap goes</summary>

- **A single tap inside the text opens the popup for the nearest Chinese character** (CJK
  Unified Ideographs, all extensions, and the compatibility ideographs), and the underline on
  the page marks the one chosen. That covers a tap on a character's glyph, between two lines,
  between two characters, in a paragraph's indent, and on punctuation (a tap on ， takes the
  nearer of its neighbours). A tap on the **pinyin drawn above a character** opens that
  character. Inside the text the page never turns.
- **The text** is each line from its first to its last character, plus 1.5 mm either side, the
  full height of the line, and the space between two lines when it is less than a line high
  (so normal paragraph spacing counts as text).
- **Every other tap is KOReader's**: the margins, the blank space after the last paragraph on a
  page, the empty rest of a short line, the space around images, and any line with no Chinese
  characters at all (an English paragraph, a line of numbers) turn the page or open the menus.
  Links and your highlights keep their usual behaviour; long-press and every other gesture are
  untouched.
- **Latin text inside a Chinese line** takes the nearest Chinese character on that line or the
  line above or below, if one is within three characters' width; if none is, the tap does
  nothing (no popup, no page turn).
- **The edge band**: a tap within **Edge pass-through width** of any screen edge always goes to
  KOReader, even on a character, so page turns stay reliable with small margins. The width is
  converted with the screen DPI KOReader reports (300 dpi if it reports none, where 5 mm is
  59 px), follows rotation, and applies from the next tap.
- KOReader's menu and corner zones reach further than the band: inside them, a tap in the text
  opens the popup; tap in the band, or outside the text, to open the menus.
- The plugin's **Status** screen shows what the last tap did: the character chosen, how far the
  tap was from it, and the time taken (a few milliseconds).
- PDF and DjVu are not supported: there, every tap is KOReader's and no pinyin is drawn.

</details>

### Line spacing

The pinyin goes in the space between lines, so while it is on the plugin sets a line height that
leaves room for it, taking KOReader's line-spacing setting into account. Turning it off restores
the book's own spacing (KOReader lays the book out again, which takes a moment).

<details>
<summary>More on line spacing</summary>

![The 临江仙 and the start of 第一回 with pinyin off (top) and on (bottom): the same lines, a little further apart with pinyin on, and qiáo over 樵 and zhǔ over 渚](docs/off-on.png)

Books with tight spacing get more pages; books that already set generous spacing can end up with
tighter lines, because the plugin replaces the book's line height rather than adding to it.

</details>

### The popup

Every popup shows the sentence around the character, then the character with all its readings (the one it has here first), its frequency rank, traditional form and components, then every dictionary word around it, longest first. Nothing guesses where the words break.

<details>
<summary>Everything in the popup, in order</summary>

The plugin reads up to 7 Chinese characters before and after the tapped one (stopping at
punctuation, a paragraph break or any non-Chinese character) and looks up every 1–8 character
stretch containing the tapped character, in simplified and traditional forms. Nothing guesses
where the words break.

- **The text around the character**, on one line at the top: as much of its sentence as fits,
  at the Chinese text size (130% of the popup's by default), the character in bold and underlined. It grows outwards from the
  character, a cut side ends in "…", and it stops at a sentence end, a paragraph break or the
  edge of the page. Popups from KOReader's dictionary that the word buttons open get the line
  too, with the whole word marked.
- **The title bar**: the tapped character on the left and, in a popup opened from the page, a
  button on the right that marks its reading here: **I know …** or **Remind me: …**
  ([Known and remind-me readings](#known-and-remind-me-readings)).
- **The tapped character first**, with all its readings. The reading drawn on the page comes
  first, unmarked (you can see it). When nothing is drawn, the reading the resolver picked comes
  first. It is marked **· likely here** only when something in the text picked it: a dictionary
  word or special word around the character, a fallback dictionary's word, or a context rule.
  When nothing did, the character's usual reading simply comes first, unlabelled, and when
  nothing decides between its two likely readings, both are listed, unmarked, the likelier first
  ([Readings](#readings)).
- **Its frequency rank**, in small grey above its own entry: **字频 4,270** is its rank among
  characters in modern written Chinese (wordfreq; 1 is the most common, and pinyin is drawn past
  3,500 by default). Past 7,000 it shows **7,000+**, as the data is too thin there for an exact
  rank, and **unranked** for a character not in the list. The source label (`CEDICT`) sits on a
  row of its own just below it. Words around the character never show one.
  With [your own frequency ranks](#your-own-frequency-ranks) on, it shows your rank, or the
  bundled one marked **(bundled)** for a character not in your books.
- **The traditional form** beside each entry's headword, smaller, when it is not the
  same: **头发** 頭髮, **中国** 中國, and nothing for 人民. A word shows the one form it is
  written with (发现 發現, 头发 頭髮). A single character with several shows them all, the one
  the word around it uses first: 发 in 头发 is **发** 髮/發, 干 in 干净 **干** 乾/干/幹. Only
  the head lines change. **Show traditional forms** in the menu turns it off.
- **Tapped in traditional characters** (a traditional book, or MOE's text in a popup), the head
  line leads with the simplified form instead, the form as tapped beside it, smaller: 頭 in 頭髮 is
  **头** 頭, the word **头发** 頭髮. A character shows the one simplified form the word around
  it uses: 乾 in 乾淨 is **干** 乾, in 乾隆 just 乾. Same setting.
- **MOE's entry for the character**, with the optional MOE dictionary: in place of CC-CEDICT's
  when CC-CEDICT lacks the character. With MOE for single characters set to **always**, under
  CC-CEDICT's entry too, cut to two lines ending in a small grey **[Tap to show more]** when
  longer; tap it to see all of it ([MOE Always](#moe-always)).
- **The character's components**, indented under its own entry ([below](#character-components)).
- **Then every dictionary word containing it**, longest first; words of the same length in
  reading order. Entries from the Chinese-language dictionaries (MOE, the 成語典, Xinhua and
  Moegirlpedia) for words CC-CEDICT lacks come last, after everything else, in larger type
  (**Chinese text size**). A word with several readings (东西 *dōngxī* "east and west" / *dōngxi*
  "thing") has the likely one marked and first.
- **The word that decides the reading** is tagged **· decides X's reading**, also when CC-CEDICT
  does not have it: then it shows a fallback dictionary's definition, or the short note of an
  unusual-reading word (冒顿 *mòdú*), or only its reading (a word from pypinyin's phrase list).
- **Buttons**: one for each entry, labelled with the character or word, which looks it up in
  KOReader's dictionary; **成语 Origin & Usage** for a chengyu with a source view; on a row of
  its own while Wi-Fi is connected, **Translate** ([below](#translating-the-sentence)); and **Close**, alone
  on the bottom row. Tapping outside the popup also closes it.
- If no dictionary has the character or any word around it, the tap goes straight to KOReader's
  dictionary lookup.

The popup is the full width of the screen (minus a small margin) and as tall as its content, up
to the full screen height, scrolling beyond that. A short popup goes in the half of the screen
away from the tapped character, so the text stays visible; a taller one is centred. While it is
open, the tapped character is **underlined on the page**, so you can see which one the tap hit;
the underline goes when the popup closes. In KOReader's night mode, the small grey lines (source labels,
字频, **spoken here**, [Tap to show more]) are drawn in the normal text colour instead, as grey
is hard to read on black e-ink.

**Chinese text in the popup is in the book's font** (**Try to match the book's font**, on by
default): every Chinese character in it, from the line at the top, the character and the
entries to the Chinese dictionaries' text, the Origin & Usage view, source labels such as 成语典
and the buttons, while English glosses, pinyin and tone marks keep KOReader's UI font. It is the
font chosen in KOReader's font menu, not a font the book embeds or sets in its CSS; a character
that font lacks comes from KOReader's usual fallback fonts. For a PDF, or when the font cannot be
loaded, the popup uses the UI font. Turned off, the popup is exactly as before.

![A popup for 观 in 阿Q正传: at the top the line 尼姑待他们走后，定了神来检点，龙牌固然已经碎在地上了，而且又不见了观音娘娘座前的一个宣德炉。 with 观 in bold and underlined, then 字频 407, the label CEDICT and 观 觀 guān · likely here with its other readings, its traditional form 觀's parts, and, labelled CEDICT, 观音 觀音 Guānyīn · decides 观's reading](docs/traditional.png)

</details>

### Tapping a character in the popup

The Chinese dictionaries' own text (MOE, the 成語典, Xinhua and Moegirlpedia: their definitions
and quotations, an idiom's short line, the Origin & Usage view) can be read by tapping: a character in it
opens its own popup on top, looked up like a tap in the book (the character and every word
around it in that text that contains it), and stays underlined in the popup below while the new
one is open. Nothing else in the popup is tappable: not the headlines (the character or word
the entry is for), the components, or the English glosses.

<details>
<summary>How popups on popups work</summary>

![Popup for 秋 in the 临江仙, its title bar with the buttons 文言 Mode and Remind me: qiū, and on top of it the popup for 歡, tapped in MOE's quotation of 〈琵琶行〉: its line at the top is 「今年歡笑復明年，秋月春風等閒度。」 with 歡 marked and no buttons in its title bar, then 字频 443 and the label CEDICT, 欢 歡 huān, its parts 雚 and 欠 labelled Wikt, 欢笑 歡笑 huānxiào labelled CEDICT, and the buttons 歡 and 歡笑, then Close at the bottom (no Translate in a popup opened from a popup)](docs/nested.png)

- **Its text is the popup's, not the book's.** The line at the top is the sentence around the
  character in the popup text: cut at 。！？；, a line break, or a closing quote after one of
  them (。」). Inside a quotation (「…」 or 『…』 with a comma or end
  mark in it), it is the whole quotation, so 秃 in 首鼠两端's 典源 gives
  「与长孺共一老秃翁，何为首鼠两端？」. A quoted word (如：「秃子」) is not a quotation.
- **Where a tap lands**: on a character, or within half a character's width of one (beside it,
  just above or below, on the punctuation next to it), takes the nearest, on the tapped line
  first. A tap anywhere else does what it did before. This holds after the popup is scrolled.
- **Close** (or the device's Back key) in a popup opened from another closes only that popup
  and shows the one below; a tap outside closes them all. Only the popup from the page has
  **Translate**. At most **5** popups are open at once (an Origin & Usage view counts); past
  that, a tap says so and opens nothing.
- **Chinese text size**: the Chinese dictionaries' text (definitions, short lines, the Origin &
  Usage view) is drawn larger than the rest of the popup, 130% by default, so its characters
  are easier to tap. The line of text from the page at the top of the popup uses the same size
  (also in KOReader's dictionary popup opened from a word button). English glosses, source labels and buttons keep the popup text size. On a
  Boox Go 7 (300 dpi) with 64 px book text and the default 60% popup text, that is 38 px
  (3.2 mm) for English and 49 px (4.2 mm) for Chinese.

</details>

### Character components

Every single-character popup shows what the character is made of, one line per part, below the
character's own entry (髡 *kūn*: 髟 *biāo* hair → meaning; 兀 *wù* → sound, loose).

<details>
<summary>Parts, sound matches, sources and coverage</summary>

- **Each part** shows its form as written, its modern reading, a short gloss and its role.
  Radical forms are read as their full character, with the common name: 氵 *shuǐ* water
  (三点水), 钅 *jīn* metal (金字旁). 阝 is 阜 on the left (左耳旁: 陈) and 邑 on the right (右耳旁: 郎).
- **Sound parts** say how well they still match: **same sound** (tone aside: 茴 / 回 *huí*),
  **same ending** (same final, medial aside: 郎 *láng* / 良 *liáng*), or **loose** (髡 *kūn* / 兀
  *wù*). Among characters outside the 2,500 most common with a sound part, about 56% are same
  sound, 20% same ending and 23% loose.
- **Ideogrammic compounds** mark every part → meaning (武: 戈 + 止); a **pictogram** or
  **indicative** character says so (象形, 指事).
- **Simplified characters** whose simplification hid a part show the traditional form's parts,
  then what replaced them (观: traditional 觀, 雚 *guàn* → sound; simplified: 雚 → 又). Where it
  only writes the same parts the simplified way (铳 from 銃, 陈 from 陳), the simplified forms are
  shown with the traditional form's roles. A character with several traditional forms (发: 發,
  髮) takes the one of the word it was tapped in, as CC-CEDICT writes it (头发: 髮; 发现: 發).
- **Sources**, in this order and labelled: **Wikt**, English Wiktionary's `Han compound`
  analysis (the first, where it records several; some describe an older form: 期, semantic 日
  from 㫷); **MMAH**, [Make Me a Hanzi](https://github.com/skishore/makemeahanzi), without its
  learner mnemonics (often wrong for simplified characters: 观 "to see 见 again 又") and without
  roles for its often-wrong "ideographic" parts, unless its note names the sound part (钺: 戉);
  **IDS**, [yi-bai/ids](https://github.com/yi-bai/ids), the structure alone (龘: 龍 + 龖).
- **Readings and glosses** of the parts come from CC-CEDICT, or Wiktionary's gloss of the sense
  a part contributes (見 "see"). A sound part takes the reading that best matches the character
  (雚 *guàn* "stork", not its default *huán*).
- **Nothing undisplayable**: an analysis with a character outside Unicode's Basic Multilingual
  Plane, which KOReader's fonts would draw as a box, gives way to the next source's (秋:
  Wiktionary's 禾 + 𤒅, then Make Me a Hanzi's 禾 + 火).

Coverage of the characters in the frequency list:

| Most common | Wikt | MMAH | IDS (structure) | None |
|---|---|---|---|---|
| 1–2,500 | 79% | 12% | 5% | 4% |
| 2,501–3,500 | 66% | 23% | 6% | 5% |
| 3,501–5,000 | 50% | 36% | 9% | 5% |
| 5,001–7,000 | 30% | 40% | 23% | 7% |
| beyond 7,000 | 17% | 18% | 56% | 8% |

Characters with none are mostly those whose only analyses contain undisplayable characters.

</details>

### Chengyu

With the optional MOE idioms or Xinhua idioms file, a chengyu gets a line of Chinese explanation and a **成语 Origin & Usage** button: its classical source, the story behind it, and examples. With these files and the MOE dictionary, every chengyu in the 46 test books gets an entry.

<details>
<summary>What the idiom files add, and how much they cover</summary>

With the optional MOE idioms or Xinhua idioms file installed, a chengyu in the popup gets more
than CC-CEDICT's English gloss:

- **One line of Chinese explanation** under CC-CEDICT's (or Wiktionary's) entry, with its own
  small label: 一毛不拔 → *形容人非常吝啬。贬义。* (成语典). It comes from MOE idioms when it has
  the chengyu, otherwise from Xinhua idioms. Entries already in Chinese get no extra line.
- **A 成语 Origin & Usage button** opens a full-screen view, in the larger Chinese size, with only **Close**,
  which returns to the popup below; any character in it can be tapped
  ([above](#tapping-a-character-in-the-popup)). From MOE idioms: 释义, the 典源 passage with its
  notes, 典故说明 (the story retold in modern Chinese), 书证, usage, examples, 辨识 and near and
  opposite idioms; a related form (玉石俱碎) adds its main idiom's source and story under that
  idiom's name. From Xinhua idioms: the explanation, the classical source and an example. MOE
  idioms comes first when both have it; with several chengyu in one popup, each button is named
  (九牛一毛 - Origin & Usage). There is no button when there is nothing beyond the one line.
- **Chengyu CC-CEDICT lacks** (精兵强将, 科班出身, 十二万分) get an entry from these files, in the
  [fallback order](#fallback-dictionaries).

Their readings appear only on their own entries and never decide the pinyin drawn. Measured with
`tools/measure_chengyu.py` on the 46 Chinese books on the test device (202,036 chengyu
occurrences) and on 临高启明 (38,398):

| Popup | 46 books | 临高启明 |
|---|---|---|
| an entry, bundled dictionaries only | 93.2% | 93.7% |
| an entry, with the MOE dictionary | 97.3% | 97.7% |
| an entry, with the MOE dictionary, MOE idioms and Xinhua idioms | 100% | 100% |
| a Chinese short line | 94.7% | 94.6% |
| an Origin & Usage view | 92.4% | 92.3% |
| an Origin & Usage view from MOE idioms | 30.3% | 28.9% |

A chengyu here is any headword CC-CEDICT tags *idiom* or either file lists, so "100%" only means
the two files cover their own lists; the gain is the 1,282 chengyu (5,397 occurrences) that had
no entry even with the MOE dictionary, such as 精兵强将, 受制于人, 由来已久.

</details>

### Classical mode

Classical mode adds one more dictionary to the popup, for reading classical Chinese (文言) and the
classical passages modern books quote. Turn it on with the **文言 Mode** button at the top right of the
popup, left of the reading-mark button, or with **Classical mode** in the Dictionaries menu: both
switch the same setting. It is off until you turn it on.

**What it adds.** With the mode on, every popup shows one extra entry for the tapped character,
labelled 文言, from the bundled **Classical dictionary**. It comes first in the popup, above the
character's CC-CEDICT entry, and is shown in full: up to five senses, in English, that classical
texts use and modern Chinese mostly doesn't: 是 *this*, 之 *him; her; it; them*, 说 (說) *yuè: to
be delighted*.

**What it doesn't change.** It only adds that one entry, and only for the tapped single character,
never for words. Pinyin on the page, the reading the popup picks, the words listed and Translate &
analyze all stay the same, and every other entry is still there, below it, in the same order. A
character with no classical senses (吗, say) gets nothing extra: its popup looks the same with the
mode on or off.

**On and off.** The button reads **文言 Mode ✓** while the mode is on and **文言 Mode** while it's off.
The setting is global: it stays on for every popup, in every book and after a restart, until you tap
the button again or untick the menu item. Popups opened from a popup's text follow it but have no
button of their own.

**Where the senses come from.** The Classical dictionary was built once, from the senses three
open dictionaries mark as classical, literary or archaic: Chinese Notes, English Wiktionary and
Unihan. An AI model (Claude Haiku) then condensed each character's senses to at most five. Every
sense has to cite the source lines it came from, and the build drops any that cite nothing. In
checks, where the sources had the sense a classical passage needed, the condensed entry kept it 95
times out of 96, and no sense was found that the sources lacked. It is still machine-condensed,
so if a sense looks odd, check it against CC-CEDICT or MOE. The details are below.

<img src="docs/classical.png" alt="Popup for 之 in 三国演义's 窦武、陈蕃谋诛之: the line 时有宦官曹节等弄权，窦武、陈蕃谋诛之，作事不密，反为所害，中涓自此愈横。 with 之 marked; the title bar, 之 on the left and the buttons 文言 Mode ✓ and Remind me: zhī on the right; first 字频 69, then the label 文言 on a row of its own and the Classical entry, in full: 之, him; her; it; them (object pronoun in non-subject position), genitive or attributive marker (possession or modification), nominalizer or subordinate-clause particle in a subject-predicate construct, this; these; that, to go; to arrive; below it, labelled CEDICT, 之 zhī (possessive particle, literary equivalent of 的 de); him; her; it; then its parts, labelled Wikt: 止 zhǐ foot → meaning, 一 yī the beginning place → meaning">

<details>
<summary>How the Classical dictionary was built, and how well it does</summary>

The dictionary covers 21,292 characters (and 184 variant forms). It was built
once by `tools/build_classical.py` from the senses three open dictionaries mark as classical,
literary or archaic: [Chinese Notes](https://github.com/alexamies/chinesenotes.com)' *Literary
Chinese* senses, English Wiktionary's, and Unihan's definitions for characters outside the 3,000
most common. Claude Haiku condensed each character's senses into at most five, citing the lines
each came from; the build drops senses that cite nothing and flags those whose words aren't in
their sources. On 128 judged words from classical texts, CC-CEDICT alone had the needed sense 84%
of the time, and with the Classical dictionary under it 95%
([research note](docs/research/classical-dictionary.md)). MOE's classical senses are not in it
(its licence does not allow it); with the MOE file installed, [MOE Always](#moe-always) shows
them.

A simplified character that stands for several traditional ones shows the one its word uses (发 in
头发: 髮 *hair*), otherwise each; a variant form (説) shows its standard form's entry (說).

</details>

### Translating the sentence

While Wi-Fi is on, the popup's Translate button sends the whole sentence around the character. With KOAssistant installed it goes to your own AI provider, for a translation and a word-by-word breakdown written for learners; without it, to KOReader's built-in translator.

<details>
<summary>How the sentence is found and sent</summary>

While Wi-Fi is on and connected, the popup from the page has one more button on a row of its
own (popups opened from a popup's text do not). It closes the
popup and sends **the whole sentence containing the tapped character**:

![Popup for 窃 at the top of the page, its line 孔乙己便涨红了脸，额上的青筋条条绽出，争辩道：“窃书不能算偷……窃书！ with 窃 marked; the buttons 文言 Mode and Remind me: qiè in the title bar; 字频 2,026, the label CEDICT, 窃 竊 qiè to steal; secretly; (humble) I, its parts 穴 xué and 切 qiè labelled MMAH, then a 窃 button, Translate & analyze the surrounding sentence [AI] and Close; above and below it the page of 孔乙己, the popup covering 窃's own line](docs/translate.png)

- **With [KOAssistant](https://github.com/zeeyado/koassistant.koplugin) installed** (tested with
  0.23.0; the button uses its internals, so a later version may fall back to the built-in
  translator), it reads **Translate & analyze the surrounding sentence [AI]**: a built-in prompt, written for learners, asks for a natural
  English translation, then every word of the sentence in order (its characters, pinyin and a
  plain-English meaning, with small words like 的 and 了 and measure words included), and a
  short note on how the sentence fits together when its structure would surprise an English
  speaker. The sentence goes to KOAssistant as a selection, so it also gets the surrounding
  context, your provider and model, and the book's title. The prompt is built into the plugin
  (temperature 0.3, up to 2000 tokens): your own custom actions do not change it, and nothing is
  written to KOAssistant's settings.
- **Without KOAssistant**, it reads **Translate** and uses **KOReader's built-in translator**.
  With "Translate from book language" on, a Chinese book whose metadata says English (common
  with converted EPUBs) comes back untranslated: set its language to zh-CN in Book information,
  or turn that option off.

The row is left out without a Wi-Fi connection; the check reads KOReader's network state only.

**The sentence** is found in the book's text, across pages: forward to the next 。！？ (or . ! ?
followed by a space) with any closing quotes after it (。” ？」), backward to just after the
previous one or the start of the paragraph. At most **200 characters** go out: a longer sentence
is cut around the tapped character, at a clause mark (，；：) when there is one close by.

</details>

## Readings

Each character's reading comes from the words around it, then context rules learned from labelled sentences, then its most frequent reading. The pinyin on the page and the reading marked in the popup always agree.

<details>
<summary>How readings are decided</summary>

Each character's reading is decided by the first of these that applies:

1. **An unusual-reading word** around it (单于 *chányú*), if
   [that option](#unusual-readings-of-common-characters) is on.
2. **A dictionary word of 2–4 characters** around it, from CC-CEDICT or pypinyin's phrase list:
   侥 is *jiǎo* in 侥幸 but *yáo* in 僬侥. When two words overlap, the more common one (by
   [wordfreq](https://github.com/rspeer/wordfreq)) wins. Longer words in the popup, up to 8
   characters, do not decide readings.
3. **A context rule** for the character next to it: 952 rules, learned from labelled Wikipedia
   sentences.
4. **A Wiktionary word**, for uncertain characters only: for the 518 characters whose most
   frequent reading is unreliable, a Wiktionary word around it can pick one of the two likeliest
   readings (累世 for 累 in 累世公卿), while that dictionary is on. Wiktionary words decide
   nothing else, since letting them override rules or reliable defaults broke more readings than
   it fixed.
5. **The character's most frequent reading.**

Particles take their neutral reading by default (吧 *ba*, 啦 *la*, 得 *de*), since their toned
readings live in words (酒吧 *jiǔbā*, 啦啦队, 得到 *dédào*). So do the commonest function words:
的 *de*, 了 *le*, 着 *zhe*, 这 *zhè*, 都 *dōu*, 还 *hái*, 与 *yǔ* and a few more are hand-checked
defaults that never show a pair; 的确 *díquè*, 了解 *liǎojiě*, 首都 *shǒudū* and the like are words. An uncertain character that nothing
decides gets both likely readings, the most likely one, or none, as **When the reading is
uncertain** says. The popup marks the same reading as the pinyin, for every character, common
ones included (的 is *dí* in 的确, *de* on its own). Some choices need the meaning, which
the plugin does not have: 东西 is always marked *dōngxi* ("thing"), also where it means "east and
west".

一 and 不 change tone in speech with the next syllable, and **Spoken tones for 一 and 不** draws
them that way, as beginners' textbooks do: 一个 *yí gè*, 一天 *yì tiān*, 不是 *bú shì*, 是不是
*shì bu shì*, 看不见 *kàn bu jiàn*. 一 stays *yī* as a number or ordinal (第一, 十一, 一九九八,
一月, 统一, 之一) and before punctuation. It is on in learner mode by default (**In learner
mode**); **Always** also draws the spoken tone above a remind-me 一 or 不 at a numeric level, and
**Never** keeps the dictionary's *yī* and *bù*. The popup's entries keep the dictionary readings,
with a grey note on the character's own entry (**spoken here: bú**), and known and remind-me marks
stay on the dictionary reading: **I know bù** hides 不 whatever its tone. On 49 books (1.5 million
一 and 不), about 800 sampled changes were judged by an AI reviewer in context: each rule was
right 97–100% of the time. Without word classes a verb and its complement (拿不到 *ná bu dào*) can't
always be told from a plain negation, so where no word confirms it, 不 keeps the dictionary's
*bù*.

Where CC-CEDICT gives a word's syllable only as a neutral tone, that is
drawn above a rare character (刺猬 *cìwei*, 鼓捣 *gǔdao*, 疙瘩 *gēda*), and its popup entry (猬
*wèi*) is marked with the same letters. When the character has several entries with those
letters, the one whose traditional form the word uses is marked (发 in 头发 *tóufa*: 髮 *fà*,
not 發 *fā*), else the word's citation tone from a short hand-checked list (处 in 好处 *hǎochu*:
*chù*; 应 in 答应 *dāying*: *yìng*), else the character's default. Where CC-CEDICT lists the word both ways (大爷 *dàyé*
"idler" / *dàye* "uncle"), the toned reading is drawn and the popup marks the neutral one.

What is drawn on a page:

- A character that gets pinyin gets it at every occurrence on the page, each in the reading it
  has there (刨 *páo* in 刨根, then *bào* in 刨子).
- A reading [marked known](#known-and-remind-me-readings) is never drawn, and one marked
  remind-me always is, whatever the level.
- When a line is too crowded for all its pinyin to fit, the pinyin of the line's most common
  annotated character is dropped first, and so on until the rest fit; the rarest are kept.

</details>

### Unusual readings of common characters

At the numeric levels common characters are not annotated, but some take a rare reading in
particular words, mostly historical names, titles and places: 单于 *chányú*, 冒顿 *mòdú*, 龟兹 *Qiūcí*, 尉迟 *Yùchí*,
番禺 *Pānyú*. With **Mark unusual readings of common characters** on, the plugin knows about 300
such words (65 hand-checked) and draws, in bold, only the characters whose reading there differs
from their usual one. A guard keeps them from matching by accident: 订单于3日发货 is 订单 + 于,
not 单于.

### Known and remind-me readings

From the popup's title bar, mark a reading **I know** (never annotated again) or **Remind me** (always annotated), in every book. Marks are kept outside the plugin's folder, so updates keep them.

<details>
<summary>How marks work, and where they are kept</summary>

A popup opened from the page has a button at the right of its title bar for the tapped
character, in the reading it has at that spot. Which button depends on whether that reading
would be drawn:

- **I know háng**: that reading never gets pinyin again, at any level and in every book. The
  character's other readings are unaffected: marking 刨 *bào* known leaves 刨 *páo* annotated.
- **Remind me: háng** (when that reading wouldn't otherwise get pinyin, usually because the
  character is common): it always gets pinyin, wherever it appears.

Once marked, the button reads **Known háng ✓** or **Reminding háng ✓**; tap it again to clear
the mark. The page changes at once, under the popup. When the reading is uncertain and both are
shown (xíng/háng), there is a button for each, and the pair is hidden only when both readings
are known. Popups opened from text inside a popup have no mark button. Marks are kept by
simplified form, so a traditional book shares them.

**Known & remind-me readings** in the menu lists the marks (`行  háng  known`); a tap on one
clears it, and **Clear all marks** clears them all after asking. The marks are kept in
`koreader/settings/chinesehelper_marks.lua`, outside the plugin's folder, so updates and
reinstalls keep them; back that file up, or copy it to another device. It is written only when
a mark changes, and atomically, so a write cut off part-way leaves the previous file. A file the
plugin can't read is never overwritten: it is renamed aside
(`chinesehelper_marks.lua.unreadable-<time>`) before the next mark is saved.

</details>

## Accuracy

Measured on the hard case, the CPP polyphone test set (Chinese Wikipedia sentences, only characters with several readings): at the default level the most likely reading is right 96.0% of the time, 97.6% counting both of a pair.

<details>
<summary>Method and full results</summary>

`tools/eval_readings.py` runs the plugin's own resolver over the test split of the
[CPP polyphone dataset](https://github.com/kakaobrain/g2pM) (labelled sentences from Chinese
Wikipedia; the context rules are learned from its train split only). CPP holds only characters
with several readings, so it is the hard case.

| Pinyin for characters outside | Characters tested | Most likely reading right | Right counting both of a pair | Shown as a pair | Estimated, ordinary text (both shown) |
|---|---|---|---|---|---|
| 1,500 most common | 5,353 | 95.7% | 97.4% | 7.0% | 99.53% |
| 2,500 | 3,189 | 95.9% | 97.5% | 7.7% | 99.50% |
| 3,500 (default) | 1,482 | 96.0% | 97.6% | 10.7% | 99.67% |
| 5,000 | 260 | 95.4% | 98.8% | 28.8% | 99.84% |
| 7,000 | 42 | 97.6% | 100.0% | 45.2% | 100.00% |

Learner mode, 500 and 1,000 have no rows. The characters they add are common ones, and the
pinyin drawn is always the reading the popup marks, so the popup's figures in the next paragraph
largely cover them.

The last column weights every character the plugin would draw by how often it occurs in ordinary
text (wordfreq), counting characters with a single reading as right. It is an estimate from
Wikipedia sentences, not a count on books, and it leans pessimistic, since CPP over-represents
minority readings. The popup's markers on the 1,000 most common characters (3,687 test examples)
are right 97.5% of the time, 98.1% counting both of a pair (3.1% shown as a pair). CPP's
sentences use 咯, 哩 and 啦 mostly in transliterations (吡咯 *luò*, 三哩岛 *lǐ*, 啦啦队): the
plugin gives them their particle readings (*lo*, *li*, *la*) as a reader of fiction meets them,
which costs 0.2–0.3 points at 1,500 and 2,500 here. CPP labels some neutral-tone words
with the full tone (枇杷 *pá*, 收拾 *shí*), which counts against the plugin's spoken form. Unusual
readings agree with CPP's label in 25 of the 36 test sentences that contain one; 8 of the 11
others are the place name 黄陂 *Huángpí*, which CPP labels *bēi*.

By what decided the reading (every test example the plugin has a reading for, common characters
included, as in the popup; a pair counts when either half is right):

| Decided by | Examples | Right | Popup label |
|---|---|---|---|
| A word (CC-CEDICT, pypinyin) | 6,584 | 98.0% | likely here |
| A special word | 78 | 85.9% | likely here |
| A fallback dictionary's word | 14 | 85.7% | likely here |
| A context rule | 919 | 99.9% | likely here |
| Nothing: the uncertainty pair | 524 | 99.2% | none (both listed) |
| Nothing: the default reading | 2,135 | 96.5% | none |

</details>

## Fallback dictionaries

For words CC-CEDICT does not have, the popup also looks in the fallback dictionaries
([the table above](#dictionaries)).

<details>
<summary>Order, labels, readings and switches</summary>

- **Order.** A word CC-CEDICT has never gets a fallback entry. Any other word shows the entry of
  the first fallback dictionary that has it, in the table's order. (CBDB's narrow office titles
  beat MOE's general definitions; an English article title is a label rather than a definition,
  so it comes after the real dictionaries; Moegirlpedia is only for words nothing else has.)
  **Order** in the **Dictionaries** menu changes it: tap a dictionary, move it with the arrows,
  then ✓. CC-CEDICT always stays first.
- **Labels.** A small grey line above an entry names its dictionary (the table's labels):
  every entry is labelled, CC-CEDICT's as **CEDICT**, so in [Classical mode](#classical-mode) the
  文言 entry and CC-CEDICT's stand apart. On the tapped character's entry the label is on its own
  row below the 字频 line. **Source labels** can turn them all off (None).
- **Readings.** A fallback entry shows its dictionary's own reading (the MOE dictionary's are
  Taiwan standard; CBDB's have no tone marks) and is never marked *likely here*:
  that marker comes from the reading resolver, so the popup and the pinyin always agree.
  Wikipedia titles and Moegirlpedia slang give no readings: the popup shows one made with
  pypinyin, marked *generated pinyin*. Only Wiktionary's words can decide a reading, for
  uncertain characters ([Readings](#readings)).
- **Switches.** Each fallback dictionary can be switched off under **Dictionaries**,
  where optional files are marked "(your own file)", or greyed out with "(not installed)".
  **Status** lists each one's version and size.

</details>

### MOE Always

CC-CEDICT's entry for a single character is short and modern: 涓 is "brook; to select". The MOE
dictionary has the classical senses too (细流。/ 姓。/ 细缓的、细微的。/ 清洁的。/ 选择。). By
default MOE's entry is shown only for a character CC-CEDICT lacks. Switch **MOE for single
characters** to **always** to see MOE's entry under CC-CEDICT's for every character; the
popup then shows both:

<details>
<summary>What the popup shows with MOE Always, and its settings</summary>

1. CC-CEDICT's entry, in full, with the 字频 rank;
2. MOE's entry for the character, labelled 國語辭典: all its readings as one block, cut to the first
   two lines as drawn, the second cut short to end in a small grey **[Tap to show more]**. Tap it
   (or the space after it) to show the rest in place; **[Tap to show less]** at the end cuts it
   again. Characters in the visible lines can
   be tapped as usual; those hidden by the cut can't;
3. the components, then the words.

MOE's readings come in the order of CC-CEDICT's (the likely one first), then those CC-CEDICT
doesn't list for the character, each marked **· not in CC-CEDICT**: about 1 in 7 characters have
one, mostly classical readings (亡 *wú* 没有, 不 *fǒu*) and some Taiwan pronunciations (侠 *jiá*).
They are shown, never used: MOE never decides the pinyin drawn on the page or the reading marked
in the popup.

Under MOE in the **Dictionaries** menu, **MOE for single characters** and **MOE for words** are
each **off**, **fallback** (only when CC-CEDICT doesn't have it) or **always**. Both default to
fallback (characters were always in 2.5.0 to 2.5.2); words set to always show MOE's
entry under CC-CEDICT's for every word around the character too. Switching MOE off turns off
both. **Collapse long entries** sets the number of lines (1, 2 or 3) or never.

Always needs a MOE file built with 2.5.0 or later, which also keeps the headwords CC-CEDICT has
(in 2.5.0, 28.2 MB instead of 17.0 MB). With an older file, Always works as fallback and **Status** says to
rebuild it: `git pull`, then `.venv/bin/python tools/build_moe.py` (or `tools/build_optional.py
--only moe --force`), and copy the new file over the old one ([below](#optional-dictionaries)).
On a Boox Go 7 the popup takes about 4 ms longer to build with MOE Always (25 ms against 21.5
ms, median of 24 taps on common characters).

</details>

### Coverage on one book

Tested on 临高启明, a novel mixing Ming officialdom, early-industrial technology and internet slang: 81% of simulated taps found a word or character the dictionaries have, and another 11.5% an everyday combination of such words.

<details>
<summary>How it was measured</summary>

The fallback dictionaries were chosen with one demanding book in mind, the time-travel novel
临高启明, which mixes Ming officialdom, early-industrial technical vocabulary and 2010s internet
slang; nothing in the plugin is specific to it. `tools/measure_book.py` split the book into words
with jieba (big dictionary, no HMM) plus words discovered in the book (元老院, 归化民), then
simulated 8,000 taps on random characters. 81% landed in a word or character the dictionaries
have, and another 11.5% in an everyday combination of such words (很多, 连连点头). Most of the
remaining 7.5% are the novel's names and coinages (髡贼, 归化民). Ming forms of address and
technical compounds are covered in part (典史 and 红夷大炮 are in; 赵老爷 and 米尼步枪 are not).

</details>

## Optional dictionaries

Five of the dictionaries can't come with the plugin: their licences allow copying them for your
own use, but not this project's distributing them. You build each one yourself on a computer, with
a script from this repository, and copy the file to the e-reader. The plugin works without them,
but they hold most of its Chinese-language explanations: the MOE dictionary alone adds 90,500
entries, and with it and the two idiom files the share of chengyu in the 46 test books that get
an entry rises from 93% to 100% ([Chengyu](#chengyu)). The screenshots on this page were taken
with all five installed.

**Which to build.** For most readers: the MOE dictionary, MOE idioms and Xinhua idioms. Add CBDB
office titles for books set in the Ming. Moegirlpedia slang adds 350 internet-slang words for a
1.4 GB download and an extra library ([below](#moegirlpedia-slang)); skip it unless you read
web fiction.

| Dictionary | Script | Download | File | Licence |
|---|---|---|---|---|
| MOE dictionary | `tools/build_moe.py` | 15 MB | 45.2 MB | [CC BY-ND 3.0 TW](https://creativecommons.org/licenses/by-nd/3.0/tw/) |
| MOE idioms | `tools/build_idioms.py` | 5 MB | 36.3 MB | [CC BY-ND 3.0 TW](https://creativecommons.org/licenses/by-nd/3.0/tw/) |
| Xinhua idioms | `tools/build_xinhua.py` | 10 MB | 14.9 MB | none for the text ([below](#the-sources)) |
| CBDB office titles | `tools/build_cbdb.py` | 140 MB (590 MB unzipped) | 0.5 MB | [CBDB Data Licensing Terms](https://cbdb.hsites.harvard.edu/cbdb-data-licensing-terms) |
| Moegirlpedia slang | `tools/build_moegirl.py` | 1.4 GB | 0.1 MB | [CC BY-NC-SA 3.0 CN](https://creativecommons.org/licenses/by-nc-sa/3.0/cn/) |

The downloads go into the clone's `build/sources/` and can be deleted afterwards.

### 1. Get the scripts

You need Python 3 and git. On a computer:

```sh
git clone https://github.com/scartoon/koreader-chinese-helper.git
cd koreader-chinese-helper
python3 -m venv .venv && .venv/bin/pip install opencc pypinyin
```

The commands are for macOS and Linux. On Windows (not tested), write `py` for `python3`,
`.venv\Scripts\pip` for `.venv/bin/pip` and `.venv\Scripts\python` for `.venv/bin/python`.

### 2. Build

One command builds the recommended three (MOE dictionary, MOE idioms, Xinhua idioms):

```sh
.venv/bin/python tools/build_optional.py
```

It prints the download size and disk space first, and at the end each file it wrote and where it
goes on the device. `--all` adds CBDB office titles; `--only moe,cbdb` builds just the ones named
(`moe`, `idioms`, `xinhua`, `cbdb`, `moegirl`). A file already built is skipped; `--force`
builds it again.

The scripts also read the plugin's database, to leave out words CC-CEDICT already has. The
repository doesn't contain it, so they take it from the latest release the first time (19 MB).

Or run one script for each dictionary you want:

```sh
.venv/bin/python tools/build_moe.py
.venv/bin/python tools/build_idioms.py
.venv/bin/python tools/build_xinhua.py
.venv/bin/python tools/build_cbdb.py
```

Each writes `build/chinesehelper-NAME.sqlite` (`chinesehelper-moe.sqlite` and so on).

### 3. Copy the files to the e-reader

They go in a `chinesehelper` folder inside KOReader's `data` folder: the `data` folder next to
the `plugins` folder you installed into. Plugin updates leave it alone, so this is done once.

- **Android** (Boox and others): `koreader/data/chinesehelper/` in the device's internal storage
  over USB (`/sdcard/koreader/data/chinesehelper/`). With adb, add `--push` to a build command
  and it copies the files there itself.
- **Other devices**: connect over USB, open the KOReader folder that holds `plugins`, make
  `data/chinesehelper/` in it if it isn't there, and copy the `.sqlite` files in.

Then restart KOReader. To check: under **Dictionaries** each file you added is marked
"(your own file)" rather than "(not installed)", and **Status** lists its version and size.

### Moegirlpedia slang

Needs the ICU library and a 1.4 GB download; worth it only if you read web fiction.

<details>
<summary>Building Moegirlpedia slang</summary>

Its source is read with the slob reader, which needs the ICU library. Install that first:

- **macOS**: `brew install icu4c pkg-config`, then
  `PKG_CONFIG_PATH=$(brew --prefix icu4c)/lib/pkgconfig .venv/bin/pip install git+https://github.com/itkach/slob.git`
- **Linux** (Debian, Ubuntu): `sudo apt install libicu-dev pkg-config`, then
  `.venv/bin/pip install git+https://github.com/itkach/slob.git`

Then `.venv/bin/python tools/build_optional.py --only moegirl` (or `tools/build_moegirl.py`),
and copy the file as in step 3. Reading every
page of the 1.4 GB snapshot takes 10–15 minutes.

</details>

### The sources

<details>
<summary>Where each optional dictionary comes from</summary>

- **MOE dictionary**: 教育部《重編國語辭典修訂本》, from
  [g0v/moedict-data](https://github.com/g0v/moedict-data). The file holds MOE's own text and a
  simplified copy ([Dictionary text](#dictionary-text)); **Status** says when a file built
  before 2.13.0 has only one.
- **MOE idioms**: 教育部《成語典》, from the ministry's
  [download page](https://language.moe.gov.tw/001/Upload/Files/site_content/M0001/respub/dict_idiomsdict_download.html)
  (the script finds the current file there). Like the MOE dictionary, its own text and a
  simplified copy.
- **Xinhua idioms**: `data/idiom.json` of [chinese-xinhua](https://github.com/pwxcoo/chinese-xinhua).
  The repository's MIT licence covers its code; the text was scraped from a published
  dictionary. The build puts back punctuation lost in scraping where that is reliable
  (首鼠鼠性多疑 → 首鼠：鼠性多疑) and shows symbols standing for lost text as …; typos stay.
- **CBDB office titles**: from the [China Biographical Database](https://cbdb.hsites.harvard.edu/)'s
  [SQLite release](https://huggingface.co/datasets/cbdb/cbdb-sqlite). Its terms are CC BY-NC-SA
  4.0 for the standalone release's data and CBDB's own non-commercial, no-derivatives,
  no-redistribution terms beyond it; this project follows the stricter: the file is for your own
  non-commercial reading.
- **Moegirlpedia slang**: from the offline snapshot
  [zhmoegirl-20230507-alpha.slob](https://github.com/aisuneko/dicts_for_aard2/releases/tag/moegirl-alpha)
  (listed on the [slob project's dictionary page](https://github.com/itkach/slob/wiki/Other-projects))
  of [萌娘百科](https://zh.moegirl.org.cn).

</details>

Whatever the licence, the files you build are for your own reading: don't share them.
[`data/README.md`](data/README.md) describes what each build keeps and changes.

## Data

### Bundled data

Everything the plugin needs is in one SQLite database (43.1 MB): CC-CEDICT, the Wiktionary and Wikipedia fallback dictionaries, the Classical dictionary, character components and the reading tables.

<details>
<summary>What the database holds</summary>

Everything the plugin needs is in one SQLite database,
`chinesehelper.koplugin/data/chinesehelper.sqlite` (43.1 MB):

- **CC-CEDICT** (`entries`): 125,397 entries, the popup's dictionary.
- **Fallback dictionaries** (`fallback`): English **Wiktionary** entries for words CC-CEDICT does
  not have (60,950), and **Chinese Wikipedia titles** (39,122): articles of 3–8 characters with
  an English article, in a technology, engineering, military or history category, less people,
  lists and some kinds of place, organisation and work (towns, stations, companies, films…;
  others remain: glaciers, museums, TV series). Neither has a row for a headword CC-CEDICT has,
  or for everyday combinations it leaves out on purpose (很多, 这次, 脸上).
- **The Classical dictionary** (`classical`, `classical_variant`): 21,292 characters' classical
  senses, at most five each, and 184 variant forms ([Classical mode](#classical-mode)).
  Its source is `data/classical.tsv.gz`, condensed once by `tools/build_classical.py`, so a
  database build needs no API key.
- **Character components** (`components`): 13,362 characters' parts, roles, readings, glosses and
  sound labels, from Wiktionary, Make Me a Hanzi and yi-bai/ids (about 2.9 MB). The database also
  holds 6,591 Wiktionary origin texts (`component_notes`) that the popup does not use.
- **The reading tables**: every character's frequency rank and default reading, words, context
  rules, uncertain characters, unusual readings. The fallback dictionaries never feed these (the
  build records their checksum, the same with and without the fallback table).

Every lookup uses an index on the simplified or traditional form (the build checks this with
`EXPLAIN QUERY PLAN`). [`data/README.md`](data/README.md) describes every table.

</details>

### Building the database

The database is not in the repository; it comes in each release's zip. You only need to build it to install from a clone.

<details>
<summary>How to build it, and its sources' versions</summary>

The database changes completely with each CC-CEDICT update, so it is **not committed** (every
rebuild would add another 36 MB of binary history); it is attached to each GitHub release inside
the ready-to-install zip. The small hand-made and learned inputs it is built from are in
[`data/`](data/README.md). To rebuild it (Python 3):

```sh
python3 -m venv .venv && .venv/bin/pip install wordfreq==3.1.1 pypinyin==0.55.0 lupa opencc
.venv/bin/python tools/build_db.py                 # downloads the current CC-CEDICT
.venv/bin/python tools/build_db.py --cedict build/cedict_1_0_ts_utf-8_mdbg.txt.gz   # or a local copy
.venv/bin/python tools/build_db.py --learn         # also re-learn the context rules (downloads the CPP dataset)
.venv/bin/python tools/build_db.py --no-wiktionary # without the Wiktionary fallback rows
.venv/bin/python tools/build_db.py --no-wikipedia  # without the Wikipedia title rows
```

The Wiktionary data (kaikki.org's extraction, about 160 MB) and the five Chinese Wikipedia SQL
dumps the titles come from (about 1.1 GB; parsing them takes a few minutes) are downloaded into
`build/sources/` when missing; the build records the dump dates, and the checksums of the other
sources, in the database's `meta` table. The release ships CC-CEDICT dated 2026-11-09 (125,397
entries), Wiktionary as of the 2026-10-01 dump (kaikki.org extraction of 2026-10-30) and Chinese
Wikipedia as of the 2026-11-01 dump; [`data/README.md`](data/README.md) lists every source's
version.

To measure what the fallback dictionaries add on your own books: `tools/fetch_books.py` (copies
the EPUBs from a USB-connected device into `build/`; `--local NAME BOOK.epub` for a book on this
computer), `tools/download_sources.sh`, then `tools/measure_fallback.py` (reports in
`build/measure/`; `--book NAME` for one book) and `tools/measure_book.py --book NAME` (what a
book still lacks, and what candidate sources would add). `tools/build_user_ranks.py` ranks
characters by the same books ([Your own frequency ranks](#your-own-frequency-ranks));
`tools/compare_user_ranks.py` compares those ranks with the bundled ones.

</details>

### Dictionary text

Each dictionary's text is shown as its source writes it: the MOE dictionary and MOE idioms in
MOE's traditional characters, Wiktionary's glosses with their Chinese as Wiktionary writes it
(`original form of 廩／廪`), CC-CEDICT's cross-references with both of its forms
(`variant of 夠|够 gòu`, `used in 鞦韆|秋千 qiūqiān`). **Popup → Dictionaries → Dictionary text →
Simplified** shows the same text in simplified characters instead (`variant of 够 gòu`), from the
next popup on. The head lines are the same either way (**头发** 頭髮), and so is the text of
dictionaries that are simplified, or English, already (Xinhua, Moegirlpedia, CBDB, Wikipedia
titles).

<details>
<summary>How the simplified text is made</summary>

Both versions are in the files, so nothing is converted on the device: the release database
(1.4 MB more for them), and MOE's and the MOE idioms' files you build (45.2 MB and 36.3 MB,
against 28.2 MB and 21.7 MB with one version). Files built before 2.13.0 hold one version (the
simplified one, unless built with the old `--traditional`), which the popup shows whatever the
setting; **Status** says to rebuild them.

The simplified text is converted at build time by `tools/simplify.py`: OpenCC `tw2s` for the
MOE dictionary and MOE idioms (Taiwan standard) and `t2s` for Wiktionary, character by character
(not `tw2sp`, which also swaps vocabulary, 滑鼠 → 鼠标, and would rewrite classical quotations).
On top of OpenCC:

- **著 meaning "to write" stays 著** (著有, 所著, 撰著, 土著, 著《…》, 书名。清王国维著。), where OpenCC
  writes 着; the aspect particle (低着头) is converted. 徵 the musical note stays 徵.
- **One character quoted in 「」 stays as written** (优恤: 「恤」文献异作「卹」): the form is the
  point. Longer quotations are converted.
- **A character whose simplified form is outside the BMP stays traditional** (九针: 鍉针, not
  𫔂针), since the device fonts would draw a box.
- **Wiktionary's "traditional／simplified" pairs** are shortened to the simplified side, a single
  character named as a form stays as written (苍铅: variant of 鉍), and Japanese is left alone.
- **CC-CEDICT** cross-references show the simplified form (`variant of 够 gòu`, `95后`).

Headwords and readings are never converted.

</details>

## Speed

On a Boox Go 7, working out a page's pinyin takes about 13 ms on average (about 50 ms on a dense page in learner mode), a tap opens the popup in about 20 ms, and the dictionaries add about 2 MB of memory.

<details>
<summary>Measurements</summary>

Measured on a Boox Go 7:

- **A page turn**: working out the pinyin for a page takes 13.4 ms on average. On a dense page
  of a history book (measured in 2.8.0) it is a median 30 ms at the default level and 51.5 ms in
  learner mode, about 200 characters annotated. The only query a page can make is one
  Wiktionary lookup, when an uncertain rare character on it is left undecided (results are
  cached).
- **First load**: the reading tables are read into memory when the first page is drawn, in about
  230 ms, once per KOReader session.
- **A tap**: from the tap to the popup built, 17–20 ms median (18–29 ms mean) with Wiktionary,
  CBDB, the MOE dictionary, Wikipedia titles and Moegirlpedia, with the Translate button showing,
  measured in 1.5, before the components, the line of text and the book's font were added. In
  2.5.0 the popup took a median 21.5 ms to build, 25 ms with [MOE Always](#moe-always).
  Each fallback dictionary adds at most one indexed query per tap; the two idiom files, each up
  to one more for their lines and Origin & Usage views, were not timed. The first tap after opening a book
  takes 20–30 ms; the optional files are opened when first needed (the MOE file in 1–3 ms).
- **Memory**: the dictionaries are read from the database, not loaded into memory; using them
  adds about 2 MB (KOReader about 133 MB in all).

</details>

## Development

Checks, tests, deploying to a device, and the evaluation tools.

<details>
<summary>Commands, tests and source files</summary>

```sh
tools/check.sh                  # luac -p and luajit -b on every Lua file, then the tests
tools/deploy.sh "/sdcard/Books/book.epub"   # check, push to a USB-connected Android device, restart KOReader
.venv/bin/python tools/eval_readings.py     # reading accuracy on the CPP test split (--fallback none: without Wiktionary's words)
.venv/bin/python tools/scan_special.py BOOK.epub   # the unusual readings a book gets
.venv/bin/python tools/make_test_epub.py build/chinesehelper-test.epub   # a book for tap tests on a device
.venv/bin/python tools/make_snippet_epub.py build/chinesehelper-snippet.epub   # a book for testing the popup's line of text on a device
.venv/bin/python tools/make_sample_epub.py  # the sample books in samples/
.venv/bin/python tools/make_screenshots.py  # the README screenshots, over adb (see below)
```

The tests (`tests/run.py`, LuaJIT through lupa) cover the reading resolver, page walking,
layout, hit testing and the edge band, the popup's content and placement, the components, the
popup's line of text around the character, MOE Always, popups opened from a popup and taps in
their text, the reading marks, the sentence finder and Translate button, the menu, and the
database code (its real SQL against the built database).
`test_integration.lua` checks that the popup marks the reading the pinyin layer draws.
`tools/check.sh` also runs the build's Python unit tests (`tests/test_*.py`, needs OpenCC): the
simplified-text converter, the idiom files' text repairs, MOE's covered rows and Wiktionary's
Standard-only readings.

| File | |
|---|---|
| `main.lua` | lifecycle, menu, data loading, old-plugin check |
| `ch_settings.lua` | settings |
| `ch_annotator.lua` | the pinyin layer: line spacing, page refresh |
| `ch_page.lua` | walks the page through the rendering engine |
| `ch_resolve.lua` | the reading resolver, for the pinyin and the popup |
| `ch_readings.lua` | the resolver's tables |
| `ch_db.lua` | the database |
| `ch_overlay.lua`, `ch_layout.lua`, `ch_hit.lua` | drawing the pinyin, spacing it, and which pinyin a tap is on |
| `ch_tap.lua` | the one tap handler, and popups opened from a popup |
| `ch_area.lua` | the text area, and the nearest character to a tap |
| `ch_edge.lua` | the edge band |
| `ch_context.lua`, `ch_text.lua` | tap → character → the characters around it; candidate words |
| `ch_pinyin.lua` | pinyin comparisons |
| `ch_popup_model.lua`, `ch_popup.lua` | what the popup shows, and the popup |
| `ch_glyphs.lua` | which character of the popup's text a tap is on, and its underline |
| `ch_marks.lua` | known and remind-me readings, and their file |
| `ch_snippet.lua` | the line of text around the tapped character, at the top of the popup |
| `ch_bookfont.lua` | the popup's faces with the book's font first, for its Chinese text |
| `ch_components.lua` | the character components lines |
| `ch_sentence.lua` | the sentence around the tapped character |
| `ch_translate.lua` | the Translate button: KOAssistant (with the built-in prompt) or KOReader's translator |

</details>

### The sample book

`samples/xiaoshuo.epub` (小说三篇) holds 《三国演义》 第一回 (the 毛宗岗 edition, which opens
with 杨慎's 临江仙), and 鲁迅's 《孔乙己》 (1919) and 《阿Q正传》 (1921), all in the public
domain. `tools/make_sample_epub.py` builds it from Chinese Wikisource (pinned revisions),
converted to simplified characters with `tools/simplify.py`; the 1938 《鲁迅全集》 text's old
glyph variants (偸, 淸, 鎗) become the standard forms and its corner quotes “”. It also builds
`samples/guwen.epub` (桃花源记, 陋室铭, 爱莲说).

### Screenshots

`tools/make_screenshots.py` retakes every image in this README on a Boox Go 7 over adb, checking each one against the plugin's own code before saving it.

<details>
<summary>How the screenshots are taken and checked</summary>

`tools/make_screenshots.py` regenerates every image in this README on a Boox Go 7 over adb: it
opens the sample book at fixed pages with fixed reader settings, taps, and saves cropped 16-grey
PNGs to `docs/`. Before an image is saved, the page's exact text goes through the plugin's own
Lua code (`tools/shot_gate.py`, with every dictionary): the pinyin drawn must be the shot's
hand-checked list, each popup must show the expected lines, and KOReader's log must agree (the
number of characters annotated, and each tap's context and reading; for a character tapped in
a popup, its sentence). Your `settings.reader.lua`
and reading marks are backed up and restored (each shot runs with no marks, or the known readings
it lists). KOAssistant's response (`translate-result`) can't be checked that
way, so it is taken only when named (`make_screenshots.py translate-result`): the script waits
for the reply to be complete, turns the viewer's pages one by one and joins them into one image,
saves its text to `build/screenshots/translate-result.txt`, and
the README's alt text for it has to be rewritten by hand to match.

</details>

## Credits and licences

The annotation code comes from **[WordGloss](https://github.com/GangYe293/wordgloss.koplugin)** by
GangYe293 (GPL-3.0): the paint layer, layout and line-height injection (`ch_overlay.lua`,
`ch_layout.lua`, parts of `ch_annotator.lua` and `ch_page.lua`). WordGloss credits its inline-gloss rendering approach to
[inlinehints.koplugin](https://github.com/omer-faruq/inlinehints.koplugin) by omer-faruq.

The code is licensed under the **GNU General Public License v3.0** (see [`LICENSE`](LICENSE)),
like WordGloss.

The data (the database, and the files in `data/`) is derived from, and distributed under,
[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/), except as noted for Make Me a
Hanzi and yi-bai/ids:

<details>
<summary>The bundled data's sources and licences</summary>

- **[CC-CEDICT](https://www.mdbg.net/chinese/dictionary?page=cc-cedict)**, © MDBG and
  contributors, CC BY-SA 4.0: the dictionary, readings and words.
- **[wordfreq](https://github.com/rspeer/wordfreq)** by Robyn Speer, data under CC BY-SA 4.0:
  character and word frequencies.
- **[pypinyin](https://github.com/mozillazg/python-pinyin)** by mozillazg, MIT License: its phrase
  list (words CC-CEDICT lacks) and fallback readings.
- The **[CPP polyphone dataset](https://github.com/kakaobrain/g2pM)** by Kyubyong Park and Seanie
  Lee (Interspeech 2020; repository Apache-2.0, sentences from Chinese Wikipedia, CC BY-SA): its
  train split, for the context rules and uncertain characters. The dataset itself is not
  included.
- **[Wiktionary](https://en.wiktionary.org/)** (English Wiktionary's Chinese entries), by
  Wiktionary contributors, CC BY-SA 4.0, via the
  [kaikki.org](https://kaikki.org/dictionary/Chinese/) extraction made with
  [wiktextract](https://github.com/tatuylonen/wiktextract) (Tatu Ylonen, "Wiktextract: Wiktionary as
  Machine-Readable Structured Data", LREC 2022): the fallback dictionary, and the `Han compound`
  analyses for the character components.
- **[Chinese Wikipedia](https://zh.wikipedia.org/)**, by Wikipedia contributors, CC BY-SA 4.0,
  from the [Wikimedia dumps](https://dumps.wikimedia.org/zhwiki/): article titles and the titles
  of their English articles (English Wikipedia, CC BY-SA 4.0), for the fallback dictionary.
- **[Make Me a Hanzi](https://github.com/skishore/makemeahanzi)** `dictionary.txt` by Shaunak
  Kishore (derived from Unihan and cjklib), under the
  [GNU LGPL v3](https://www.gnu.org/licenses/lgpl-3.0.html) or later: decompositions and
  etymology types for the character components. The components rows taken from it (labelled
  MMAH) are under the LGPL v3; the licence text is in the plugin folder (`LGPL-3.0.txt`, with
  the GPL v3 it refers to, `GPL-3.0.txt`), and the build script that derives them is
  `tools/components.py`. Its `graphics.txt` (Arphic licence) is not used.
- **[yi-bai/ids](https://github.com/yi-bai/ids)** by Yi Bai, MIT License: character structures
  (`ids_lv2.txt`) for the components of characters no other source analyses.
- The **Classical dictionary** (`data/classical.tsv.gz`, the `classical` table), CC BY-SA 4.0,
  condensed by Claude Haiku from: **[Chinese Notes](https://github.com/alexamies/chinesenotes.com)**
  dictionary, © Fo Guang Shan 佛光山 2013–2025, CC BY-SA 3.0 (its *Literary Chinese* senses,
  adapted under 4.0);
  English **Wiktionary** (above); and the **[Unihan database](https://www.unicode.org/charts/unihan.html)**
  `kDefinition` and variant fields, © Unicode, Inc.,
  [Unicode License v3](https://www.unicode.org/license.txt).

</details>

Not distributed, never in the repository or a release; tools in `tools/` build them from the
originals for the user's own device ([Optional dictionaries](#optional-dictionaries) links each
licence):

<details>
<summary>The optional dictionaries' sources and licences</summary>

- the MOE dictionary, 中華民國教育部《[重編國語辭典修訂本](https://dict.revised.moe.edu.tw/)》,
  © Ministry of Education, Republic of China (Taiwan), CC BY-ND 3.0 TW, read from
  g0v/moedict-data (`tools/build_moe.py`);
- CBDB office titles, from the China Biographical Database (Harvard University, Academia Sinica
  and Peking University), CBDB Data Licensing Terms and CC BY-NC-SA 4.0 (`tools/build_cbdb.py`);
- MOE idioms, 中華民國教育部《[成語典](https://dict.idioms.moe.edu.tw/)》, © Ministry of Education,
  Republic of China (Taiwan), CC BY-ND 3.0 TW (`tools/build_idioms.py`);
- Xinhua idioms, from chinese-xinhua's `data/idiom.json` (text scraped from a published
  dictionary) (`tools/build_xinhua.py`);
- Moegirlpedia slang, from 萌娘百科 by its contributors, CC BY-NC-SA 3.0 CN, via a third party's
  offline snapshot (`tools/build_moegirl.py`).

</details>

[`data/README.md`](data/README.md) lists the changes made to each source and the versions used.
The texts in
the sample books are in the public domain: `samples/xiaoshuo.epub` (罗贯中, 鲁迅; from
[Chinese Wikisource](https://zh.wikisource.org/)) and `samples/guwen.epub` (陶渊明, 刘禹锡, 周敦颐).
