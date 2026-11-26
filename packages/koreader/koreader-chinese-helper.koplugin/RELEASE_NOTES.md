# v2.29.0 · 2026-11-26


CBDB: well-known people, office titles of every dynasty, book titles (#87)
- `tools/build_cbdb.py` builds a new CBDB file (8.7 MB, still your own file, never shared): 381
  well-known people (dates, 字, 號, 諡, home town, 進士 year), 25,822 office titles of three or more
  characters from every dynasty (with CBDB's English), and 35,297 book titles. Until now it held
  2,900 Ming office titles. Rebuild it to get the new entries; Status says so for an old file.
- What is in it was decided by testing CBDB on 150,000 simulated taps in 50 books and judging
  1,358 matches in context (`tools/measure_cbdb.py`). People are those another dictionary also
  knows (69 of 70 right), office titles leave out modern ones like 副总裁 (93% right), and book
  titles show only when the tapped text is exactly a title in 《》 (109 of 109). Alternative names
  (字, 號), places and lesser-known people were left out: CBDB has ordinary words among them
  (知道 is somebody's 字), so they were mostly wrong.
- CBDB entries show only where the word fits the plugin's word segmentation (not 试百户 inside
  考试百户).
- Readings take their tones from CC-CEDICT, matched to CBDB's toneless pinyin (王安石 Wáng
  Ānshí; 单 Shàn as a surname); CBDB's own letters stay where nothing settles a tone.
- In menus and on Status, "CBDB office titles" is now just "CBDB".

CBDB on by default, right after CC-CEDICT, even for words CC-CEDICT has (#88)
- With the CBDB file installed, CBDB's entry now comes right after CC-CEDICT's for the same word,
  collapsed like MOE Always and before MOE's own Always entry: 王安石's dates, 字, 號, home town
  and 進士 year under CC-CEDICT's one line. With **Words first**, each word's CBDB entry follows
  its CC-CEDICT entry; in **Classical mode** the 文言 entry stays at the top.
- A new **CBDB** item under CBDB's switch in the **Dictionaries** menu: off / fallback (only words
  CC-CEDICT lacks, as before) / always (the default). Status shows the mode.
- CBDB is now first in the order after CC-CEDICT. **If you had saved your own order, CBDB is moved
  to its front once**; the rest of your order is kept, and you can move CBDB back with **Order**.
- About 6 taps in 1,000 get a CBDB entry in the books it was tested on.

# v2.28.0 · 2026-11-26


MOE's dictionaries come with the plugin, unmodified (#86)
- 教育部《重編國語辭典修訂本》 and 《成語典》 are now in the release zip (`data/moe/`): nothing to
  build. They come straight from MOE's own downloads (2026-09-29), not g0v/moedict-data, and hold
  every record and every field exactly as MOE publishes them. They ship with MOE's usage notes
  (使用說明) and a `LICENSE.txt` with the CC BY-ND 3.0 TW licence and MOE's attribution, which
  Status also shows.
- MOE's text is always shown as MOE writes it, in traditional characters. **Dictionary text:
  Simplified** no longer applies to MOE or the 成語典, since the licence doesn't allow changing
  them.
- A MOE definition now shows MOE's whole definition field, line by line: part-of-speech labels
  ([名]), sense numbers, examples and quotations (until now: the bare sense from g0v's copy).
  Collapsed to two lines under MOE Always, as before.
- A related idiom's short line keeps MOE's own punctuation: 即「胸有成竹」。比喻處事有定見。
  (it was 即「胸有成竹」：比喻…). A line of the 成語典 holding one of MOE's image codes
  (&25cd1.jpg;) is now left out instead of shown as code (31 idioms).
- MOE files you built yourself (`chinesehelper-moe.sqlite`, `chinesehelper-idioms.sqlite` in
  KOReader's data folder) are no longer read. Status says they can be deleted.
  `tools/build_idioms.py` is gone; `tools/build_moe.py` now builds the bundled folder.
- Sizes: release zip 23.4 MB → 57.7 MB; `data/moe/moe.sqlite` 78.6 MB unzipped (the two
  self-built files were 45.2 MB and 36.3 MB); the main database is unchanged.
- Entries: 重編國語辭典 163,909 records, all of them in the file (before: 153,041 rows kept from
  g0v's copy). The popup looks up 153,140, 90,519 of them for words CC-CEDICT lacks (before:
  90,501); everyday combinations and headwords that are not 1–8 Han characters stay in the file
  but are not looked up, as before. 成語典 5,489 records, 5,474 looked up, 3,705 for idioms
  CC-CEDICT lacks (before: 5,473 and 3,704).
- The reading tables are unchanged: MOE still never decides the pinyin drawn.

# v2.27.0 · 2026-11-25


Learner-mode accuracy on the reader's own books (#35)
- Measured: 300 random occurrences of characters with several readings, from 10 held-out
  books, judged by Claude. About 98.7% get the right letters and tone; 94.0% counting pairs
  (得 *de/děi*) and neutral-tone differences as wrong. The README's Accuracy section has the
  details.
- Fixed the four errors it found: 咳咳 (a cough) *ké ké*, adverb + 地点头 *de diǎn tóu*, the
  rank title 五大夫 *wǔ dà fū*, and the name 李泌 *Lǐ Bì*.
- g2pW (a neural model) was compared over 262,634 sampled occurrences. Most of its
  disagreements were its own Taiwan readings (和 *hàn*, 包括 *guā*), so no other fixes came from it.

# v2.26.0 · 2026-11-25

Neutral tones of everyday words in learner mode (#83)
- Learner mode now draws the neutral tone of common words the dictionary gives one: 时候
  *shí hou*, 事情 *shì qing*, 回来 *huí lai*, 明白 *míng bai*, 名字 *míng zi*, 朋友 *péng you*
  (447 words). Before, a word whose characters each have only one reading had no reading of
  its own, so 时候 was drawn *shí hòu*.
- Also inside longer words that the dictionary writes with full tones: 做生意 *zuò shēng yi*,
  到时候, 儿媳妇, 发脾气, 晒太阳, 做买卖 and a few more.
- Only learner mode is affected: the other settings never draw these characters.

Reduplicated words (#77)
- Repeated characters that no dictionary lists as a word now take one reading instead of the
  uncertainty pair: 尽尽 *jìn jìn*, 撇撇嘴 *piě piě*, 写写画画 *xiě xiě*, 咋咋呼呼 *zhā zhā*
  (it showed *zǎ/zé*), 长长的 *cháng cháng*, 晕晕乎乎, 挑挑拣拣 and about 40 more, found in
  the reader's own books.
- Repeats that are not one word keep their readings: 都得得罪 (*děi dé*), 吐蕃蕃部.

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
