# v0.12.20 · 2026-11-05

## Release Highlights
* Vocabulary: You can now build a vocabulary list, mark words as Learning or Mastered for Word Lens hints, and sync with Anki
* Statistics: Added a reading statistics dashboard so you can see your reading habits at a glance
* Reading: Added Page Flip and paper curl page turns, a page preview while dragging the progress slider, a straight-line reading ruler, and keyboard-only text selection
* Styling: You can now ignore publisher fonts, make white image backgrounds transparent, and adjust dialogue highlighting
* Text-to-Speech: You can now preview voices, pick a default voice per language, and sync downloaded read-aloud audio across devices
* Library: You can now import pasted text and Word or RTF files, share collections as bundles, search for covers in the app
* Sync: Added Grimmory, Obsidian, and CrossPoint 2.0 highlight sync, a new view of where your reading data goes, and a switch for servers with self-signed certificates
* Dictionary: You can now resize the dictionary popup, customize AI context lookups, edit word hints, and choose your lookup app on Android
* PDF: Text is now sharper, especially on iOS and Android, with smoother pinch zoom, panning, and gapless horizontal scrolling
* More: The KOReader plugin can sign in with a QR code, iPhone Duo gets book mode on its inner display, and stylus annotation and sync are more reliable

## What's Changed
<details>
<summary>Click to expand</summary>

* feat(library): show the full book or group title on hover by @chrox in https://github.com/readest/readest/pull/6785
* fix(reader): keep the footer bar off the horizontal scrollbar when zoomed by @chrox in https://github.com/readest/readest/pull/6786
* fix(sync): keep imported annotations through the next sync (#6762) by @chrox in https://github.com/readest/readest/pull/6787
* fix(reader): release closed reader views from the cached book document, closes #6710 by @chrox in https://github.com/readest/readest/pull/6788
* fix(tts): skip bare superscript note markers when reading aloud by @chrox in https://github.com/readest/readest/pull/6791
* chore(agent): maintenance loops with a Reply Desk, lessons and acceptance rules by @chrox in https://github.com/readest/readest/pull/6796
* fix(reader): let the battery percentage follow a custom footer text color by @chrox in https://github.com/readest/readest/pull/6798
* fix(layout): clip nowrapped lines along the line only, keeping footnote icons whole by @chrox in https://github.com/readest/readest/pull/6801
* fix(sync): push a highlight made right after a notes sync by @chrox in https://github.com/readest/readest/pull/6802
* chore: declare tsx for the worktree scripts and clean up merged worktrees in the triage loop by @chrox in https://github.com/readest/readest/pull/6807
* chore(deps): bump the github-actions group with 8 updates by @dependabot[bot] in https://github.com/readest/readest/pull/6812
* fix(deps): resolve open Dependabot alerts by @chrox in https://github.com/readest/readest/pull/6813
* fix(reader): highlight long and nested quoted dialogue by @chrox in https://github.com/readest/readest/pull/6814
* fix(layout): keep the indent on paragraphs with a footnote icon by @chrox in https://github.com/readest/readest/pull/6828
* fix(android): tighten the e-ink device identity whitelist by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6833
* fix(i18n): improve Turkish translations and add missing keys by @AlBPanda in https://github.com/readest/readest/pull/6830
* fix(android): force light native chrome on e-ink devices by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6799
* fix(bookshelves): list filter values only from books still in the library by @jadhavgaurav in https://github.com/readest/readest/pull/6835
* ci: guard the e-ink identity whitelist against Rust/Kotlin drift by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6834
* fix(reader): leave a footnote marker out of a double-click or long-press word by @chrox in https://github.com/readest/readest/pull/6808
* fix(annotator): run quick actions on a selection made in the footnote popup by @chrox in https://github.com/readest/readest/pull/6809
* fix(koplugin): give the Readest Library menu KOReader's UI for CoverBrowser by @chrox in https://github.com/readest/readest/pull/6845
* fix(annotations): import ReadEra backups that split documents across docs_N.json by @chrox in https://github.com/readest/readest/pull/6846
* fix(tts): hold the view still while a note is being typed during Read Aloud by @chrox in https://github.com/readest/readest/pull/6849
* fix(tts): keep the sentence being read across the paragraph look-ahead by @chrox in https://github.com/readest/readest/pull/6860
* fix(reader): open external links with their query string by @chrox in https://github.com/readest/readest/pull/6861
* fix(reader): follow a link inside a table instead of zooming the table by @chrox in https://github.com/readest/readest/pull/6862
* fix(reader): don't make a table that fits scroll because of a link at its edge by @chrox in https://github.com/readest/readest/pull/6882
* fix(annotator): look up the next word in the footnote popup on desktop by @chrox in https://github.com/readest/readest/pull/6886
* fix(md): render $ and $$ math in Markdown books by @chrox in https://github.com/readest/readest/pull/6887
* fix(reader): break the page for page breaks in inline styles by @chrox in https://github.com/readest/readest/pull/6888
* fix(reader): keep book colors that only start like #000 by @chrox in https://github.com/readest/readest/pull/6883
* fix(reader): let a book's own hover style underline its links by @chrox in https://github.com/readest/readest/pull/6884
* fix(reader): show the toolbar on a center tap in a scrolled comic by @chrox in https://github.com/readest/readest/pull/6885
* fix(tts): keep a note's focus when a navigation ends during Read Aloud by @chrox in https://github.com/readest/readest/pull/6889
* fix(desktop): drag the window from an unfocused title-bar search field by @chrox in https://github.com/readest/readest/pull/6893
* fix(epub): bound native zip entry reads during import by @chrox in https://github.com/readest/readest/pull/6817
* fix(api): validate DeepL and AI gateway request limits by @chrox in https://github.com/readest/readest/pull/6818
* chore(agent): lessons from 2026-10-14 to 10-15 by @chrox in https://github.com/readest/readest/pull/6842
* fix(reader): normalize section media types before sanitizing by @chrox in https://github.com/readest/readest/pull/6819
* fix(library): park a finished book as unread when an updated build is re-keyed by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6871
* fix(reader): keep the chosen sidebar tab while Read Aloud plays by @chrox in https://github.com/readest/readest/pull/6847
* fix(reader): sanitize book markup rendered in the app window by @chrox in https://github.com/readest/readest/pull/6815
* fix(reader): don't fail opening a book whose section is still loading by @chrox in https://github.com/readest/readest/pull/6903
* fix(kosync): send and read FB2 positions in crengine's FictionBook form by @chrox in https://github.com/readest/readest/pull/6905
* feat(sync): per-server switch for self-signed certificates by @chrox in https://github.com/readest/readest/pull/6822
* refactor(sync): share the note merge rule between Readest Cloud and file sync by @chrox in https://github.com/readest/readest/pull/6843
* fix(sync): verify a redirect off a self-signed server's origin by @chrox in https://github.com/readest/readest/pull/6931
* fix(tts): support Xiaomi MiMo chat-completions speech synthesis by @izengyx in https://github.com/readest/readest/pull/6863
* fix(tts): accept a pasted speech endpoint as a custom TTS base URL by @chrox in https://github.com/readest/readest/pull/6906
* fix(reader): drive the percent readout from the continuous reading fraction by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6876
* fix(nix): stabilize the dev shell and share Linux runtime dependencies by @Kasifrasi in https://github.com/readest/readest/pull/6851
* fix(storage): check the quota after reserving the row and keep clients off files writes by @chrox in https://github.com/readest/readest/pull/6820
* fix(translate): keep long sentences whole for Yandex and retry rate-limited chunks by @Columpio in https://github.com/readest/readest/pull/6919
* fix(reader): limit pdf zoom in preview to MAX_ZOOM_LEVEL by @jelly-afk in https://github.com/readest/readest/pull/6904
* fix(tts): prepare the next paragraphs' first sentence while one plays by @smist37 in https://github.com/readest/readest/pull/6910
* fix(eink): master scrim switch for capture-blocking overlays by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6922
* fix(proxy): normalize hostnames and validate resolved addresses by @chrox in https://github.com/readest/readest/pull/6821
* fix(opds): drop decoded-body headers from proxied error responses by @chrox in https://github.com/readest/readest/pull/6942
* fix(opds): vary cached proxy feeds on the Authorization header by @chrox in https://github.com/readest/readest/pull/6946
* fix(metadata): reject impossible publication dates by @kelvinalfaro in https://github.com/readest/readest/pull/6937
* fix(reader): pinch a PDF spread without jumping sideways on release by @chrox in https://github.com/readest/readest/pull/6943
* fix(reader): show the every-occurrence toggle's state on e-ink by @chrox in https://github.com/readest/readest/pull/6948
* fix(hardcover): preserve legacy mappings when migration writes fail by @kelvinalfaro in https://github.com/readest/readest/pull/6938
* fix(reader): keep word-final apostrophes inside single-quoted dialogue by @chrox in https://github.com/readest/readest/pull/6950
* fix(reader): detect the language of Markdown and HTML books with none declared by @chrox in https://github.com/readest/readest/pull/6952
* fix(reader): keep the bars hidden when the window gives focus back by @chrox in https://github.com/readest/readest/pull/6954
* fix(tts): read PDF words across line breaks, and hyphenated words whole by @chrox in https://github.com/readest/readest/pull/6955
* fix(sync): say when the device clock keeps changes from syncing by @chrox in https://github.com/readest/readest/pull/6956
* fix(kosync): send and read MOBI positions in crengine's HTML form by @chrox in https://github.com/readest/readest/pull/6951
* fix(translate): leave ruby readings out of the text sent to the translator by @chrox in https://github.com/readest/readest/pull/6953
* fix(pdf): keep PDF text sharp at fractional display scales by @chrox in https://github.com/readest/readest/pull/6949
* fix(reader): keep word-final apostrophes before a dash inside single-quoted dialogue by @chrox in https://github.com/readest/readest/pull/6957
* fix(tts): read a PDF aloud in the language of its page by @Armone0 in https://github.com/readest/readest/pull/6944
* fix(reader): dismiss the selection toolbar on a click beside the text by @chrox in https://github.com/readest/readest/pull/6961
* fix(reader): keep the mouse Back button in the book when it's released off the page by @chrox in https://github.com/readest/readest/pull/6963
* fix(pdf): don't select text while a drag pans the page by @chrox in https://github.com/readest/readest/pull/6962
* fix(reader): add touch-accessible web fullscreen by @kelvinalfaro in https://github.com/readest/readest/pull/6964
* fix(reader): use the correct form of 2 in Chinese footer numbers by @RaphaelFakhri in https://github.com/readest/readest/pull/6966
* fix(reader): pinch a PDF spread with one finger on each page by @chrox in https://github.com/readest/readest/pull/6968
* fix(reader): keep the tabular-nums utility effective below Chromium 119 by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6970
* fix(reader): give the remaining-info readout tabular-nums like its siblings by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6971
* fix(android): keep the reading position when the screen wakes by @chrox in https://github.com/readest/readest/pull/6972
* fix(library): wrap the select-mode action bar instead of clipping it by @chrox in https://github.com/readest/readest/pull/6973
* fix(library): keep the title bar draggable in select mode by @chrox in https://github.com/readest/readest/pull/6978
* fix(reader): turn a fixed-layout page by a drag across the page, not the cell by @chrox in https://github.com/readest/readest/pull/6983
* chore(deps): bump the github-actions group with 6 updates by @dependabot[bot] in https://github.com/readest/readest/pull/6981
* fix(ios): play narration and TTS through the native player on iPad by @chrox in https://github.com/readest/readest/pull/6979
* fix(reader): hide the bars when the pointer crosses their edge strip into the book by @chrox in https://github.com/readest/readest/pull/7005
* feat(library): add .rbooks collection bundle export and import by @Armone0 in https://github.com/readest/readest/pull/6945
* fix(reader): show selection toolbar after off-text mouse release by @kelvinalfaro in https://github.com/readest/readest/pull/6988
* fix(import): name the files a mixed drag-drop skips by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6991
* fix(reader): dismiss footnote popup in Paragraph mode by @kelvinalfaro in https://github.com/readest/readest/pull/6996
* fix(reader): keep Russian prepositions with quoted words by @kelvinalfaro in https://github.com/readest/readest/pull/6998
* chore(deps): bump webpki chain for the emSign/eMudhra intermediate CA distrust by @k6G52m4Dz75W in https://github.com/readest/readest/pull/7002
* fix(tts): play stored narration audio in place instead of copying it by @chrox in https://github.com/readest/readest/pull/7004
* fix(deps): resolve open Dependabot alerts by @chrox in https://github.com/readest/readest/pull/7007
* fix(import): map a ZIP with no book inside to "format not supported" by @kelvinalfaro in https://github.com/readest/readest/pull/6997
* chore(deps): bump the dompurify override floor to 3.4.17 by @k6G52m4Dz75W in https://github.com/readest/readest/pull/7003
* fix(android): play stored narration audio in place from the book file by @chrox in https://github.com/readest/readest/pull/7010
* fix(handwriting): keep undo history and new strokes when a drawing syncs by @chrox in https://github.com/readest/readest/pull/7014
* fix(pdf): keep a pan going past the page edge and turning at the end by @chrox in https://github.com/readest/readest/pull/7012
* feat(stats): add reading statistics dashboard by @realdanvanth in https://github.com/readest/readest/pull/6986
* fix(docker): bump node base image to 24.22.1 for the 2026-10 Node security releases by @k6G52m4Dz75W in https://github.com/readest/readest/pull/7016
* fix(reader): keep the header with the pointer on the top edge of a maximized window by @chrox in https://github.com/readest/readest/pull/7017
* fix(ios): play stored narration audio in place from the book file by @chrox in https://github.com/readest/readest/pull/7019
* fix(koplugin): connect over IPv4 in forked sync workers on macOS by @chrox in https://github.com/readest/readest/pull/7021
* Import pasted text into the library by @kelvinalfaro in https://github.com/readest/readest/pull/6992
* feat(notion): colour highlight quotes and send notes as callouts by @chrox in https://github.com/readest/readest/pull/7029
* fix(rsvp): keep Bengali vowel signs and conjuncts with the focus letter by @chrox in https://github.com/readest/readest/pull/7028
* fix(handwriting): re-measure the page after a push page turn by @chrox in https://github.com/readest/readest/pull/7030
* fix(deps): bump next to 16.4.2 for the open Dependabot alerts by @chrox in https://github.com/readest/readest/pull/7032
* fix(annotator,notion): keep a highlight's colour on Annotate; Notion note template; working sync links by @chrox in https://github.com/readest/readest/pull/7031
* fix(reader): fit cover image to page in paginated mode and preserve aspect ratio by @Armone0 in https://github.com/readest/readest/pull/7027
* ci(android-e2e): retry the emulator system image install by @chrox in https://github.com/readest/readest/pull/7036
* Add native Android paper curl and stabilize page turns by @sadikh94 in https://github.com/readest/readest/pull/7001
* fix(audiobook): stream paired local audio through the media proxy on desktop (#6848) by @chrox in https://github.com/readest/readest/pull/7037
* feat(ios): turn pages with the native paper curl by @chrox in https://github.com/readest/readest/pull/7046
* fix(tts): resume a mid-sentence pause in place from media keys by @chrox in https://github.com/readest/readest/pull/7069
* feat(tts): keep the chosen sleep timer for the rest of the app launch by @chrox in https://github.com/readest/readest/pull/7070
* fix(sync): keep a position read just before closing the book by @chrox in https://github.com/readest/readest/pull/7071
* fix(layout): keep a percentage-width image next to text at its size by @chrox in https://github.com/readest/readest/pull/7072
* feat(library): accept docx and rtf imports via silent EPUB conversion by @k6G52m4Dz75W in https://github.com/readest/readest/pull/7050
* fix(reader): jump to a typed page when the field loses focus by @chrox in https://github.com/readest/readest/pull/7080
* fix(storage): delete a book file uploaded under its hash name by @chrox in https://github.com/readest/readest/pull/7063
* feat(library): Manage Cache on desktop by @chrox in https://github.com/readest/readest/pull/7066
* fix(build): turn off the Turbopack build cache that Next 16.4 enables by @chrox in https://github.com/readest/readest/pull/7082
* fix(dictionaries): create the database folder before opening it by @chrox in https://github.com/readest/readest/pull/7076
* fix(tts): step back into the previous page at its last sentence by @chrox in https://github.com/readest/readest/pull/7077
* fix(library): sort a subgroup by its own name inside a parent group by @chrox in https://github.com/readest/readest/pull/7081
* fix(annotator): keep a dragged selection handle on its line by @Armone0 in https://github.com/readest/readest/pull/7053
* fix(tts): open the Workers Edge TTS socket over cloudflare:sockets by @smist37 in https://github.com/readest/readest/pull/7056
* fix(library): open a .zip of images as a comic by @chrox in https://github.com/readest/readest/pull/7078
* feat(reader): calibrate the page-number readout with real screen counts by @k6G52m4Dz75W in https://github.com/readest/readest/pull/7060
* fix(reader): keep native curl pages when a turn redraws unchanged highlights by @chrox in https://github.com/readest/readest/pull/7112
* feat(reader): preview the page under the progress slider while dragging by @chrox in https://github.com/readest/readest/pull/7110
* fix(handwriting): keep the pen fine on wide desktop pages by @chrox in https://github.com/readest/readest/pull/7109
* fix(reader): keep the screen awake after the window is refocused on Linux by @chrox in https://github.com/readest/readest/pull/7108
* fix(novel): recognize 第N頁 and traditional chapter units in chapter titles by @chrox in https://github.com/readest/readest/pull/7107
* fix(reader): keep a note's own styling in the footnote popup by @chrox in https://github.com/readest/readest/pull/7111
* fix(reader): compare curl overlay markup in paint order and check new overlays by @chrox in https://github.com/readest/readest/pull/7114
* fix(reader): keep native curl pages when progress sync starts by @chrox in https://github.com/readest/readest/pull/7115
* fix(library): retry a synced cover whose download failed by @chrox in https://github.com/readest/readest/pull/7116
* fix(reader): never open the media viewer for note-reference markers or chapter-length tables by @doublex640 in https://github.com/readest/readest/pull/7083
* fix(build): make pnpm preview serve pages and rewrites again by @chrox in https://github.com/readest/readest/pull/7141
* fix(reader): stamp sections loaded after a theme switch with the live theme by @chrox in https://github.com/readest/readest/pull/7121
* fix(reader): show the page's own rendering in the image viewer by @doublex640 in https://github.com/readest/readest/pull/7096
* fix(reader): give volume keys back when Use Volume Keys is turned off by @chrox in https://github.com/readest/readest/pull/7140
* ci: pin the Playwright jobs to ubuntu-24.04 by @chrox in https://github.com/readest/readest/pull/7151
* chore(deps): bump the github-actions group with 7 updates by @dependabot[bot] in https://github.com/readest/readest/pull/7149
* feat(reader): Page Flip page-turn style on Android, iOS and desktop by @chrox in https://github.com/readest/readest/pull/7160
* fix(crosspoint): link a reader's copy to an Audiobookshelf ebook (#7086) by @ts-eva in https://github.com/readest/readest/pull/7087
* test(reader): unmount each image-gallery test's viewer by @chrox in https://github.com/readest/readest/pull/7163
* fix(kosync): sync an Audiobookshelf ebook under its file's id (#7088) by @chrox in https://github.com/readest/readest/pull/7161
* fix(hardcover): reuse journal entries already on Hardcover instead of duplicating them by @chrox in https://github.com/readest/readest/pull/7162
* fix(hardcover): sign in through Readest's own Hardcover OAuth app by @chrox in https://github.com/readest/readest/pull/7165
* fix(reader): stop translation DOM work after the hook unmounts by @chrox in https://github.com/readest/readest/pull/7167
* feat(library): page count badge on covers as a per-bookshelf option (#6909) by @Armone0 in https://github.com/readest/readest/pull/7142
* feat(ios): book mode on iPhone Duo's inner display by @wemcdonald in https://github.com/readest/readest/pull/7137
* feat(tts): let custom TTS services set their audio format and voices by @sunnymodi21 in https://github.com/readest/readest/pull/7155
* fix(annotations): save exports to storage on Android and clear the bottom inset by @chrox in https://github.com/readest/readest/pull/7169
* fix(ios): keep the orientation lock when the scene is resizable by @wemcdonald in https://github.com/readest/readest/pull/7146
* fix(tts): upload existing downloaded packs when sync is on, skip listening cache by @chrox in https://github.com/readest/readest/pull/7176
* fix(nix): add missing build/runtime dependency by @dastarruer in https://github.com/readest/readest/pull/7170
* fix(kosync): read xpointers with explicit [1] steps from newer crengine by @bercedev in https://github.com/readest/readest/pull/7172
* test(kosync): check both xpointer forms against crengine at two DOM versions by @chrox in https://github.com/readest/readest/pull/7178
* feat(reader): swipe past a zoomed PDF page's edge to turn, like Photos by @sunnymodi21 in https://github.com/readest/readest/pull/7175
* fix(sync): stop opening a "Sync failed" dialog for file-sync errors by @chrox in https://github.com/readest/readest/pull/7183
* fix(ui): stop the plan cards clipping on iOS 16, closes #7181 by @chrox in https://github.com/readest/readest/pull/7184
* fix(tts): stop caching, packing and syncing the same sentence twice by @chrox in https://github.com/readest/readest/pull/7187
* fix(desktop): reopen the in-app browser window at its last size and position by @NeilN1 in https://github.com/readest/readest/pull/7185
* fix(tts): give up on a silent Edge connection after 30s on every transport by @chrox in https://github.com/readest/readest/pull/7188
* feat(sync): sync downloaded read-aloud audio through Readest Cloud and every file-sync backend by @chrox in https://github.com/readest/readest/pull/7177
* fix(android): keep the page-turn cover below the keyboard, closes #7171 by @chrox in https://github.com/readest/readest/pull/7191
* feat(sync): record each book's synced read-aloud packs in its config by @chrox in https://github.com/readest/readest/pull/7190
* feat(koplugin): sign in with a QR code; fix the logged-out label and global logout (#7186) by @chrox in https://github.com/readest/readest/pull/7192
* fix(sync): list every page of a book's cloud files for synced data by @chrox in https://github.com/readest/readest/pull/7199
* fix(reader): disable separate cover in scroll layouts by @kelvinalfaro in https://github.com/readest/readest/pull/7195
* fix(reader): hide dismissed footer immediately by @kelvinalfaro in https://github.com/readest/readest/pull/7197
* fix(reader): keep the screen awake while speed reading plays by @chrox in https://github.com/readest/readest/pull/7200
* fix(reader): wrap long text in scroll mode by @kelvinalfaro in https://github.com/readest/readest/pull/7196
* ci: run the web browser tests in their own job by @chrox in https://github.com/readest/readest/pull/7202
* chore(agent): update agent memories by @chrox in https://github.com/readest/readest/pull/7203
* fix(android): continue recorded narration while screen locked by @kelvinalfaro in https://github.com/readest/readest/pull/7194
* feat(settings): search the font lists in Font settings by @chrox in https://github.com/readest/readest/pull/7204
* fix(library): keep two FB2 documents that share a title and author (#7150) by @chrox in https://github.com/readest/readest/pull/7205
* fix(tts): keep the page when Read Aloud reads text the book hides by @chrox in https://github.com/readest/readest/pull/7207
* feat(reader): improve stylus annotations and finger navigation by @chrox in https://github.com/readest/readest/pull/7213
* fix(koplugin): wait for Wi-Fi before pulling on wake by @chrox in https://github.com/readest/readest/pull/7215
* feat(reader): choose tap or long press to open the image viewer per book by @chrox in https://github.com/readest/readest/pull/7208
* fix(library): add stable colored placeholder covers by @chrox in https://github.com/readest/readest/pull/7222
* fix(opds): allow trusted private catalogs at runtime by @chrox in https://github.com/readest/readest/pull/7225
* fix(tts): start Storyteller narration at the current text by @chrox in https://github.com/readest/readest/pull/7223
* fix(windows): make Explorer thumbnails opt-in by @chrox in https://github.com/readest/readest/pull/7220
* fix(android): open linked images on touch hold by @chrox in https://github.com/readest/readest/pull/7221
* fix(tts): publish downloaded audio records without a page turn by @chrox in https://github.com/readest/readest/pull/7224
* fix(opds): match equivalent trusted IPv6 literals by @chrox in https://github.com/readest/readest/pull/7226
* fix(reader): navigate paragraphs with volume buttons by @chrox in https://github.com/readest/readest/pull/7227
* fix(reader): allow gapless horizontal PDF scrolling by @chrox in https://github.com/readest/readest/pull/7232
* fix(tts): keep skipped utterances from aborting replacement speech by @chrox in https://github.com/readest/readest/pull/7233
* fix(tts): show a custom TTS voice's listed name instead of its id by @onedge in https://github.com/readest/readest/pull/7229
* test(novel): make failed image placeholders deterministic by @chrox in https://github.com/readest/readest/pull/7236
* fix(sync): ignore stale duplicate reading positions by @chrox in https://github.com/readest/readest/pull/7231
* fix(reader): highlight continued multi-paragraph dialogue by @chrox in https://github.com/readest/readest/pull/7238
* test: use four workers for unit tests by @chrox in https://github.com/readest/readest/pull/7242
* fix(tts): play local AAC narration natively on Linux by @chrox in https://github.com/readest/readest/pull/7240
* fix(ios): capture readable shared pages when loading stalls by @chrox in https://github.com/readest/readest/pull/7241
* feat(dictionary): customize context prompts and response limits by @chrox in https://github.com/readest/readest/pull/7244
* fix(security): remediate Dependabot dependency alerts by @chrox in https://github.com/readest/readest/pull/7248
* fix(library): preserve original filenames and use PDF filename titles by @chrox in https://github.com/readest/readest/pull/7237
* fix(reader): release volume keys while reader controls are open by @chrox in https://github.com/readest/readest/pull/7254
* fix(reader): highlight long punctuated single-quoted dialogue by @chrox in https://github.com/readest/readest/pull/7255
* feat(reader): add dialogue highlighting weight options by @chrox in https://github.com/readest/readest/pull/7256
* feat(kosync): support original filename checksums by @chrox in https://github.com/readest/readest/pull/7253
* feat(library): add searchable history dropdown by @chrox in https://github.com/readest/readest/pull/7261
* fix(account): require explicit confirmation before deleting account by @chrox in https://github.com/readest/readest/pull/7258
* fix(ios): decode imported file URL basenames once by @chrox in https://github.com/readest/readest/pull/7263
* test(reader): handle cancelled paginator previews in browser tests by @chrox in https://github.com/readest/readest/pull/7267
* feat(ios): add fullscreen system dictionary setting by @chrox in https://github.com/readest/readest/pull/7269
* fix(library): ignore leading English articles in title sorting by @chrox in https://github.com/readest/readest/pull/7271
* feat(reader): make white image backgrounds transparent by @chrox in https://github.com/readest/readest/pull/7270
* feat(reader): show background textures in footnote popups by @chrox in https://github.com/readest/readest/pull/7268
* feat(android): choose the system dictionary lookup app (#4937) by @chrox in https://github.com/readest/readest/pull/7272
* perf(web): run the web Worker near Supabase with Smart Placement by @chrox in https://github.com/readest/readest/pull/7273
* perf(api): stop hot sync routes loading the TTS engine and DOMPurify by @chrox in https://github.com/readest/readest/pull/7274
* feat(translator): add a Thinking setting to custom LLM translators, fix translator field sync by @chrox in https://github.com/readest/readest/pull/7275
* fix(sync): sign bucket-root listings with a trailing slash by @gilgamesh-tkh in https://github.com/readest/readest/pull/7278
* fix(dictionary): stream context dictionary responses by @chrox in https://github.com/readest/readest/pull/7285
* fix(sync): support provider downloads and generic transfer history by @chrox in https://github.com/readest/readest/pull/7289
* feat(reader): add a straight-line reading ruler by @chrox in https://github.com/readest/readest/pull/7288
* feat(vocabulary): vocabulary builder and Learning/Mastered marks for Word Lens by @chrox in https://github.com/readest/readest/pull/7284
* feat(metadata): search for book covers in app by @chrox in https://github.com/readest/readest/pull/7290
* fix(koplugin): collect sync workers before KOReader exits by @chrox in https://github.com/readest/readest/pull/7293
* fix(reader): keep the sidebar button top-left on tablets, tidy the transparent-image row by @chrox in https://github.com/readest/readest/pull/7294
* chore(agent): update memories by @chrox in https://github.com/readest/readest/pull/7295
* fix(bookorbit): let the web proxy run on Cloudflare Workers by @chrox in https://github.com/readest/readest/pull/7296
* feat(reader): vim-style find to start and extend a selection from the keyboard by @you-gao in https://github.com/readest/readest/pull/7282
* fix(library): refresh external sources without a Readest login by @chrox in https://github.com/readest/readest/pull/7297
* fix(reader): use platform-specific spread defaults by @chrox in https://github.com/readest/readest/pull/7299
* perf(reader): subscribe the vim command line to the store fields it uses by @chrox in https://github.com/readest/readest/pull/7301
* feat(reader): ignore publisher font names by font category by @chrox in https://github.com/readest/readest/pull/7298
* fix(reader): draw PDF text at the screen's full resolution on iOS and Android by @chrox in https://github.com/readest/readest/pull/7300
* fix(reader): preserve publisher font lists and category fallbacks by @chrox in https://github.com/readest/readest/pull/7302
* fix(bookdrop): keep received file names inside the inbox by @chrox in https://github.com/readest/readest/pull/7304
* fix(auth): keep the sign-in callback URL out of logs by @chrox in https://github.com/readest/readest/pull/7305
* fix(annotator): line the note card up with its popup box by @chrox in https://github.com/readest/readest/pull/7310
* feat(annotator): draw a global annotation's copies as a dashed underline by @chrox in https://github.com/readest/readest/pull/7309
* fix(send): allow PATCH through CORS so the apps can approve a sender by @chrox in https://github.com/readest/readest/pull/7312
* fix(sync): sync a re-enabled or cleared custom TTS field to other devices by @BEMELON in https://github.com/readest/readest/pull/7307
* feat(tts): read aloud with Speech Dispatcher voices on Linux by @chrox in https://github.com/readest/readest/pull/7314
* feat(vocabulary): redesign the mobile header by @chrox in https://github.com/readest/readest/pull/7315
* feat(crosspoint): sync CrossPoint 2.0 clippings with Readest highlights by @chrox in https://github.com/readest/readest/pull/7317
* fix(annotator): clear a moved highlight's old anchors on the server too by @chrox in https://github.com/readest/readest/pull/7319
* fix(sync): give HTML chapter files their own sync identity by @chrox in https://github.com/readest/readest/pull/7321
* fix(reader): reach the last page when a book ends partway into a spread by @chrox in https://github.com/readest/readest/pull/7320
* feat(tts): preview voices and pick a default voice per language by @chrox in https://github.com/readest/readest/pull/7322
* feat(library): remove selected books from the device only by @chrox in https://github.com/readest/readest/pull/7324
* fix(sync): stop idle notes pushes and keep what a push leaves out by @chrox in https://github.com/readest/readest/pull/7326
* chore(deps): bump actions-rust-lang/setup-rust-toolchain from 2.0.0 to 2.0.1 in the github-actions group by @dependabot[bot] in https://github.com/readest/readest/pull/7331
* fix(kosync): follow a percentage-only position on PDFs and push 1-based pages by @chrox in https://github.com/readest/readest/pull/7334
* feat(vocabulary): sync with Anki on Android by @chrox in https://github.com/readest/readest/pull/7328
* feat(reader): vim-style find selects text in PDFs too by @chrox in https://github.com/readest/readest/pull/7333
* ci(codeql): use advanced setup and skip Rust analysis on PRs without Rust changes by @chrox in https://github.com/readest/readest/pull/7335
* fix(reader): shrink default list indent under Override Book Layout by @chrox in https://github.com/readest/readest/pull/7338
* chore(tts): shorten Readest Voice download windows to 16 sentences or 512 chars by @chrox in https://github.com/readest/readest/pull/7339
* fix(wordlens): hint a word that ends where an inline element starts or ends by @chrox in https://github.com/readest/readest/pull/7340
* feat(sync): add a Grimmory integration (#7337) by @chrox in https://github.com/readest/readest/pull/7341
* fix(tts): preview voices at the player's speed by @chrox in https://github.com/readest/readest/pull/7345
* fix(reader): keep native curl pages in step with the toolbars and panels by @chrox in https://github.com/readest/readest/pull/7343
* feat(reader): move menu options to Settings and add Vocabulary to the view menu by @chrox in https://github.com/readest/readest/pull/7348
* fix(sync): match books for Grimmory stats alone, and undo a failed connect by @chrox in https://github.com/readest/readest/pull/7347
* fix(tts): play Media Overlay clips whose text target is an image by @chrox in https://github.com/readest/readest/pull/7352
* feat(dictionary): resize the dictionary popup from a corner grip (#7344) by @chrox in https://github.com/readest/readest/pull/7354
* feat(integrations): sync highlights into an Obsidian vault on desktop and Android by @chrox in https://github.com/readest/readest/pull/7349
* fix(wordlens): hint Learning phrases of two or more words by @chrox in https://github.com/readest/readest/pull/7350
* fix(auth): send password sign-in through a Worker on readest.com by @chrox in https://github.com/readest/readest/pull/7355
* fix(dictionary): give the popup's resize grip a 32px hit area by @chrox in https://github.com/readest/readest/pull/7357
* test(dictionary): drag the resize grip from a hit-tested point outside the popup by @chrox in https://github.com/readest/readest/pull/7359
* feat(dictionary): edit a Learning word's hint in the dictionary popup by @chrox in https://github.com/readest/readest/pull/7356
* fix(wordlens): match phrases on token edges, retry after a rejected match by @chrox in https://github.com/readest/readest/pull/7358
* fix: reader search, e-ink paging, cache and koplugin delete from user reports by @chrox in https://github.com/readest/readest/pull/7360
* fix(reader): apply Open Images to every book and to tables by @chrox in https://github.com/readest/readest/pull/7363
* chore(agent): update agent memories by @chrox in https://github.com/readest/readest/pull/7365
* feat(integrations): show where reading data flows and what is working by @chrox in https://github.com/readest/readest/pull/7366
* fix(tts): stream staged narration audio so a long chapter can't kill the app on Android by @chrox in https://github.com/readest/readest/pull/7367
* release: version 0.12.20 by @chrox in https://github.com/readest/readest/pull/7368

</details>

## New Contributors
* @AlBPanda made their first contribution in https://github.com/readest/readest/pull/6830
* @izengyx made their first contribution in https://github.com/readest/readest/pull/6863
* @Kasifrasi made their first contribution in https://github.com/readest/readest/pull/6851
* @jelly-afk made their first contribution in https://github.com/readest/readest/pull/6904
* @Armone0 made their first contribution in https://github.com/readest/readest/pull/6944
* @RaphaelFakhri made their first contribution in https://github.com/readest/readest/pull/6966
* @realdanvanth made their first contribution in https://github.com/readest/readest/pull/6986
* @sadikh94 made their first contribution in https://github.com/readest/readest/pull/7001
* @doublex640 made their first contribution in https://github.com/readest/readest/pull/7083
* @wemcdonald made their first contribution in https://github.com/readest/readest/pull/7137
* @sunnymodi21 made their first contribution in https://github.com/readest/readest/pull/7155
* @bercedev made their first contribution in https://github.com/readest/readest/pull/7172
* @NeilN1 made their first contribution in https://github.com/readest/readest/pull/7185
* @onedge made their first contribution in https://github.com/readest/readest/pull/7229
* @gilgamesh-tkh made their first contribution in https://github.com/readest/readest/pull/7278
* @you-gao made their first contribution in https://github.com/readest/readest/pull/7282
* @BEMELON made their first contribution in https://github.com/readest/readest/pull/7307

**Full Changelog**: https://github.com/readest/readest/compare/v0.12.16...v0.12.20

# v0.12.16 · 2026-10-13

## Release Highlights
* Text-to-Speech: Added Readest Voice premium read-aloud voices for Plus and Pro, you can now connect your own OpenAI-compatible voice service, and Edge voices work again
* Annotations: You can now handwrite and draw on your pages, and share passages as quote card images
* Library: Books now show their page count with a new Pages sort and filter that syncs across devices, and numbered titles sort in natural order
* Sync: Custom fonts download when you need them and can be removed from the cloud, custom theme edits now sync, and deleted books no longer come back
* Sync: KOReader progress sync and WebDAV sync are more reliable, and signing out only logs out the current device
* Reading: Very large or link-heavy chapters no longer freeze the reader, and fixed layout issues with headings, blockquotes, footnotes, and background textures
* Audiobooks: Audiobookshelf playback now works in the web app, chapters are detected more reliably, and you can pair audiobooks with books streamed from Audiobookshelf
* Linux: Fixed a freeze with two open windows, the main window reopens maximized, and Reveal in Folder works again
* PDF: You can hide page thumbnails in the PDF table of contents
* More: The share sheet opens again on iOS 16, with polish for the drawing tools, bottom sheets, and bookshelf header

## What's Changed
* chore(android): link WebView APK downloads in the outdated-WebView dialog by @chrox in https://github.com/readest/readest/pull/6649
* chore(deps): bump DeterminateSystems/determinate-nix-action from 3.22.5 to 3.23.0 in the github-actions group by @dependabot[bot] in https://github.com/readest/readest/pull/6679
* ui: place the "Log out" item in the second sub menu by @5w5 in https://github.com/readest/readest/pull/6645
* fix(reader): stop link-heavy single-file sections from hanging by @chrox in https://github.com/readest/readest/pull/6678
* refactor(ai): drop write-only indexingStates map in ragService by @irontaek in https://github.com/readest/readest/pull/6687
* Use music-metadata for audiobook chapters by @Borewit in https://github.com/readest/readest/pull/6686
* feat(reader): render huge sections in chunks by @chrox in https://github.com/readest/readest/pull/6680
* fix(koreader): reliable progress sync with hardened auth and error handling by @ivanovsergey93 in https://github.com/readest/readest/pull/6684
* fix(linux): stop the CEF focus loop that froze two-window sessions by @chrox in https://github.com/readest/readest/pull/6691
* fix(bookorbit): stamp the chapter on synced notes and bookmarks (#6655) by @bianyukun1213 in https://github.com/readest/readest/pull/6658
* fix(reader): read section text when a non-CJK lang hides CJK content by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6672
* fix(library): stamp deletes so the sync merge cannot undelete the book, closes #6663 by @itsmunzir in https://github.com/readest/readest/pull/6682
* fix(opds): keep the feed scroll position after opening a book by @jadhavgaurav in https://github.com/readest/readest/pull/6683
* fix(library): use natural sorting for numbered titles by @kelvinalfaro in https://github.com/readest/readest/pull/6693
* fix(nix): refresh pnpmDeps hash for music-metadata by @chrox in https://github.com/readest/readest/pull/6688
* fix(kosync): keep the server path when proxying KOSync requests by @chrox in https://github.com/readest/readest/pull/6698
* fix(build): keep music-metadata out of the web server bundle by @chrox in https://github.com/readest/readest/pull/6699
* fix(reader): offer Pair Audiobook for EPUBs streamed from Audiobookshelf (#6695) by @ts-eva in https://github.com/readest/readest/pull/6697
* feat(reader): share passages as quote card images by @chrox in https://github.com/readest/readest/pull/6701
* fix(send): poll the inbox every 5 minutes instead of every minute by @chrox in https://github.com/readest/readest/pull/6706
* feat(tts): Readest Voice, premium read-aloud voices for Plus and Pro by @chrox in https://github.com/readest/readest/pull/6720
* fix(tts): connect Edge TTS to the new api.msedgeservices.com endpoint by @chrox in https://github.com/readest/readest/pull/6722
* fix(tts): count queued Readest Voice downloads against the listening quota by @chrox in https://github.com/readest/readest/pull/6721
* Support handwriting annotation by @esmaeelE in https://github.com/readest/readest/pull/6674
* perf(api): verify access tokens locally with getClaims by @chrox in https://github.com/readest/readest/pull/6724
* chore(agent): update agent memories by @chrox in https://github.com/readest/readest/pull/6725
* fix(auth): limit explicit logout to the current session by @hulkbig in https://github.com/readest/readest/pull/6709
* chore(auth): point clients at the Supabase project URL by @chrox in https://github.com/readest/readest/pull/6729
* feat(tts): move Readest Voice into its own service by @chrox in https://github.com/readest/readest/pull/6732
* fix(tts): make Readest Voice downloads responsive and tell users about quota by @chrox in https://github.com/readest/readest/pull/6736
* fix(tts): Readest Voice downloads that resume and follow the voice, and read aloud that survives a slow engine by @chrox in https://github.com/readest/readest/pull/6738
* fix(tts): resume queued downloads with the session's voice by @chrox in https://github.com/readest/readest/pull/6739
* fix(sync): decode XML entities in WebDAV PROPFIND hrefs by @smist37 in https://github.com/readest/readest/pull/6741
* fix(reader): keep the CJK widow/orphan lift alive under Use Book Layout by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6711
* fix(rss): rebuild feed book TOC on every open instead of using the nav cache by @christi4nity in https://github.com/readest/readest/pull/6718
* fix(android): resolve Temp to the app cache so narration and file staging work on older Android by @ChristophWally in https://github.com/readest/readest/pull/6714
* fix(reader): honor justification overrides in footnote popups by @kelvinalfaro in https://github.com/readest/readest/pull/6708
* fix(audiobook): request Audiobookshelf audio with CORS on the web app (#6696) by @ts-eva in https://github.com/readest/readest/pull/6707
* docs(tts): drop the RunPod settings from the web env example by @chrox in https://github.com/readest/readest/pull/6744
* fix(library): retire re-keyed book hashes with a tombstone row (last import wins) by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6703
* fix(tts): send Sec-MS-GEC v2 tokens to Edge TTS by @chrox in https://github.com/readest/readest/pull/6751
* feat(tts): custom OpenAI-compatible TTS services by @chrox in https://github.com/readest/readest/pull/6746
* fix(reader): suppress the webview context menu in the desktop app by @chrox in https://github.com/readest/readest/pull/6752
* fix(linux): make Reveal in Folder work again, closes #6660 by @chrox in https://github.com/readest/readest/pull/6754
* feat(reader): add a toggle to hide PDF page thumbnails in the TOC, closes #6650 by @chrox in https://github.com/readest/readest/pull/6756
* fix(linux): restore the maximized main window on launch, closes #6657 by @chrox in https://github.com/readest/readest/pull/6757
* fix(layout): give inline-only blockquotes the paragraph margin under Override Book Layout by @chrox in https://github.com/readest/readest/pull/6759
* fix(settings): reset the animation style to Push with Reset Behavior, closes #6753 by @chrox in https://github.com/readest/readest/pull/6760
* fix(tts): keep Read Aloud and its highlights intact after the sign-in detour by @chrox in https://github.com/readest/readest/pull/6758
* feat(sync): download synced custom fonts on demand, delete them from the cloud by @chrox in https://github.com/readest/readest/pull/6761
* fix(layout): let a more specific left-align beat a centered heading rule, closes #6723 by @chrox in https://github.com/readest/readest/pull/6763
* fix(metadata): allow 0 as a series index by @chrox in https://github.com/readest/readest/pull/6764
* fix(reader): keep the progress label in place while dragging the slider, closes #6646 by @chrox in https://github.com/readest/readest/pull/6766
* fix(style): keep Override Book Color working over a background texture, closes #6712 by @chrox in https://github.com/readest/readest/pull/6765
* fix(reader): measure image tap zones on its column in a two-page spread, closes #6745 by @chrox in https://github.com/readest/readest/pull/6769
* feat(calibre): add multi-language support by @GOSENGWONG in https://github.com/readest/readest/pull/6768
* fix(reader): keep the image long-press menu working on Android PDF pages by @chrox in https://github.com/readest/readest/pull/6771
* fix(ios): open the share sheet on iOS 16 for files with spaces or non-ASCII names, closes #6719 by @chrox in https://github.com/readest/readest/pull/6770
* build(android): ship per-ABI APKs (arm64, armv7, legacy) instead of universal by @chrox in https://github.com/readest/readest/pull/6772
* feat(library): count pages at import, add Pages sort and filter, closes #6662 by @chrox in https://github.com/readest/readest/pull/6774
* feat(sync): sync the import-time page count across devices by @chrox in https://github.com/readest/readest/pull/6775
* chore(agent): update agent memories by @chrox in https://github.com/readest/readest/pull/6776
* fix(sync): detect in-place custom theme changes by @anirudhqwerty in https://github.com/readest/readest/pull/6777
* fix: iOS reader polish for drawing dock, short sheets, bookshelf header and read aloud by @chrox in https://github.com/readest/readest/pull/6778
* release: version 0.12.16 by @chrox in https://github.com/readest/readest/pull/6779

## New Contributors
* @5w5 made their first contribution in https://github.com/readest/readest/pull/6645
* @irontaek made their first contribution in https://github.com/readest/readest/pull/6687
* @Borewit made their first contribution in https://github.com/readest/readest/pull/6686
* @ivanovsergey93 made their first contribution in https://github.com/readest/readest/pull/6684
* @bianyukun1213 made their first contribution in https://github.com/readest/readest/pull/6658
* @ts-eva made their first contribution in https://github.com/readest/readest/pull/6697
* @esmaeelE made their first contribution in https://github.com/readest/readest/pull/6674
* @smist37 made their first contribution in https://github.com/readest/readest/pull/6741
* @christi4nity made their first contribution in https://github.com/readest/readest/pull/6718
* @ChristophWally made their first contribution in https://github.com/readest/readest/pull/6714
* @GOSENGWONG made their first contribution in https://github.com/readest/readest/pull/6768
* @anirudhqwerty made their first contribution in https://github.com/readest/readest/pull/6777

**Full Changelog**: https://github.com/readest/readest/compare/v0.12.12...v0.12.16

# v0.12.12 · 2026-10-04

## Release Highlights
* Text-to-Speech: You can now listen sentence by sentence and loop a passage with A-B repeat, control playback from your desktop's Now Playing controls
* Reading: Added dialogue highlighting for quoted speech, a Column Gap setting for two-page spreads
* Sync: Added a Readest plugin for CrossPoint e-readers for reading progress sync
* Sync: You can now sync reading progress to Pagebound, sign in to Hardcover more easily, and note edits are no longer overwritten by older synced copies
* PDF: PDFs now blend smoothly with your reading theme with smart image inversion, show page thumbnails in the table of contents
* PDF: Highlighting and text selection on scanned PDFs is smoother and more accurate, and very large scanned pages no longer crash the reader on iOS
* Translation: You can now add your own translation providers with a reusable prompt library, look up words with an AI context dictionary
* Annotations: A global note now appears on every occurrence of its text, exports can include the sentence around each highlight
* Android: Added home screen widgets for your current book and bookshelf, automatic e-ink full refresh every few page turns
* More: Images now have a long-press and right-click menu to copy or save them, Windows shows PDF thumbnails in Explorer

## What's Changed
* fix(koplugin): fix sync on Android, library pull ANR, and Rescan library by @chrox in https://github.com/readest/readest/pull/6364
* chore(agent): add koreader-e2e skill for on-device plugin testing by @chrox in https://github.com/readest/readest/pull/6366
* fix(reader): fall back to saving a file when the gallery save fails by @chrox in https://github.com/readest/readest/pull/6367
* fix(windows): drop the broken native shadow on Windows 10 by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6362
* perf(android): cut the arm64 apk from 90MB to 57MB by @chrox in https://github.com/readest/readest/pull/6368
* fix(build): repair the Docker and Nix builds after #6368 by @chrox in https://github.com/readest/readest/pull/6379
* fix(settings): reset update preferences with behavior settings by @hulkbig in https://github.com/readest/readest/pull/6369
* fix(android): open Readest from TTS media controls by @kelvinalfaro in https://github.com/readest/readest/pull/6370
* fix(reader): handle footnote links in paragraph mode by @hulkbig in https://github.com/readest/readest/pull/6365
* feat(reader): add dialogue highlighting for quoted speech by @WantenMN in https://github.com/readest/readest/pull/6376
* chore(deps): bump the github-actions group with 7 updates by @dependabot[bot] in https://github.com/readest/readest/pull/6387
* fix(annotator): clear the pre-drag range when a highlight is resized by @hulkbig in https://github.com/readest/readest/pull/6357
* fix(reader): keep the sidebar toggler in place when the sidebar opens by @chrox in https://github.com/readest/readest/pull/6435
* fix(payment): revoke one-time Stripe purchases on refund by @chrox in https://github.com/readest/readest/pull/6436
* fix(android): detect e-ink readers whose manufacturer prop reports the SoC vendor by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6392
* refactor(settings): organize the font panel around the role each font plays by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6325
* fix(settings): restore scroll position on reopen by @WantenMN in https://github.com/readest/readest/pull/6389
* fix(web): decode binary files read as text by @WestXu in https://github.com/readest/readest/pull/6402
* fix(library): skip copying a book file onto itself on import by @WestXu in https://github.com/readest/readest/pull/6403
* fix(backup): restore orphan books whose library row was deleted by @WestXu in https://github.com/readest/readest/pull/6405
* fix(sync): push existing notes on the first open of a book by @WestXu in https://github.com/readest/readest/pull/6404
* fix(reader): keep the footer clear of rounded screen corners on Android by @davidfvaquero in https://github.com/readest/readest/pull/6429
* perf(reader): parallelize the EPUB open path by @shiningsprk-arch in https://github.com/readest/readest/pull/6406
* fix(telemetry): stop PostHog traffic when the setting is off by @itsmunzir in https://github.com/readest/readest/pull/6434
* feat(widget): configurable Android bookshelf widget by @RedHatter in https://github.com/readest/readest/pull/6430
* fix(windows): draw the missing window frame on Windows 10 by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6399
* fix(koplugin): prompt to log in again when the session has expired by @chrox in https://github.com/readest/readest/pull/6445
* fix(koplugin): avoid crash when synced position can't be resolved by @stantonb in https://github.com/readest/readest/pull/6441
* fix(sync): refuse Readest Cloud book uploads while Books sync is off by @chrox in https://github.com/readest/readest/pull/6446
* feat(widget): improve bookshelf widget configuration by @RedHatter in https://github.com/readest/readest/pull/6440
* feat(settings): reverse mouse wheel paging and hide e-ink bookshelf buttons by @chrox in https://github.com/readest/readest/pull/6448
* fix(reader): update chapter pages left on every page turn by @chrox in https://github.com/readest/readest/pull/6447
* fix(tts): let the play/pause media key resume TTS on desktop by @chrox in https://github.com/readest/readest/pull/6452
* fix(sync): stop creating OneDrive folders that Graph now rejects by @chrox in https://github.com/readest/readest/pull/6451
* fix(library): skip hidden subdirectories when scanning folders to import by @chrox in https://github.com/readest/readest/pull/6453
* docs(sync): make the write-parent precondition provider-neutral by @chrox in https://github.com/readest/readest/pull/6455
* fix(library): page the e-ink library with volume keys by @chrox in https://github.com/readest/readest/pull/6456
* feat(tts): native desktop Now Playing for macOS, Windows and Linux by @chrox in https://github.com/readest/readest/pull/6457
* fix(nix): add the desktop Now Playing crates to Cargo.cef.lock by @chrox in https://github.com/readest/readest/pull/6459
* fix(reader): turn the page when tapping a page-filling image by @chrox in https://github.com/readest/readest/pull/6458
* fix(library): skip per-book toasts for bulk downloads by @chrox in https://github.com/readest/readest/pull/6463
* feat(annotator): make keeping the selection after an instant lookup optional by @chrox in https://github.com/readest/readest/pull/6460
* fix(koplugin): remove sync response files left behind by exit-time syncs by @chrox in https://github.com/readest/readest/pull/6461
* fix(ios): resume audiobook natively after a CarPlay interruption ends by @chrox in https://github.com/readest/readest/pull/6462
* feat(reader): import MHTML web archives, closes #6413 by @chrox in https://github.com/readest/readest/pull/6464
* fix(annotator): close selection popup after choosing a highlight color by @kelvinalfaro in https://github.com/readest/readest/pull/6465
* fix(reader): close lookup popups when their selection is cleared by @chrox in https://github.com/readest/readest/pull/6467
* fix(sidebar): keep the annotations list still when the clicked note is visible by @chrox in https://github.com/readest/readest/pull/6468
* feat(tts): pause longer after questions, exclamations and ellipses, closes #6412 by @chrox in https://github.com/readest/readest/pull/6469
* fix(library): keep Date Read order when grouping, tagging or editing metadata by @chrox in https://github.com/readest/readest/pull/6470
* test(player): fix flaky podcast session-end tests by @chrox in https://github.com/readest/readest/pull/6472
* fix(reader): keep the footer clear of rounded screen corners on iPhone by @chrox in https://github.com/readest/readest/pull/6474
* fix(reader): hold the horizontal pan lock through momentum swipes on iOS by @chrox in https://github.com/readest/readest/pull/6475
* fix(reader): keep note editor and highlight toolbar open in footnote popups, closes #6395 by @chrox in https://github.com/readest/readest/pull/6477
* fix(transfer): allow uploads and downloads under a custom data location, closes #6383 by @chrox in https://github.com/readest/readest/pull/6478
* chore(agent): update agent memories by @chrox in https://github.com/readest/readest/pull/6479
* fix(library): center the empty library state again by @chrox in https://github.com/readest/readest/pull/6482
* ci(android): give the Android build step 90 minutes by @chrox in https://github.com/readest/readest/pull/6483
* fix: empty library state over a lingering search, and a dropped dictionary card tap by @chrox in https://github.com/readest/readest/pull/6485
* fix(backup): save iOS backups through the share sheet instead of hanging at 0%, closes #6375 by @chrox in https://github.com/readest/readest/pull/6486
* chore(linux): catch up the CEF runtime with upstream feat/cef, closes #6397 by @chrox in https://github.com/readest/readest/pull/6487
* fix(library): download selected Audiobookshelf items for offline from select mode by @chrox in https://github.com/readest/readest/pull/6489
* feat(backup): include reading statistics in library backups, closes #6488 by @chrox in https://github.com/readest/readest/pull/6490
* fix(reader): remove the line between zoomed images in Webtoon Mode, closes #6484 by @chrox in https://github.com/readest/readest/pull/6491
* test(paginator): rest before release so the drag test commits on distance alone by @chrox in https://github.com/readest/readest/pull/6493
* fix(desktop): open books in a new window after closing another reader, closes #6363 by @chrox in https://github.com/readest/readest/pull/6496
* fix(desktop): reopen the library when Readest is relaunched with only reader windows open, closes #6394 by @chrox in https://github.com/readest/readest/pull/6495
* fix(search): ignore soft hyphens when searching book text, closes #6384 by @chrox in https://github.com/readest/readest/pull/6494
* fix(ui): stop iOS 16 reloading to the library when a toggle or slider renders, closes #6355 by @chrox in https://github.com/readest/readest/pull/6497
* feat(annotations): optionally export the sentence around each highlight, closes #6352 by @chrox in https://github.com/readest/readest/pull/6498
* feat(tts): skip Hanja glosses after Hangul in Korean text by @chrox in https://github.com/readest/readest/pull/6500
* feat(annotator): show a global note on every occurrence of its text, closes #6186 by @chrox in https://github.com/readest/readest/pull/6501
* feat(settings): give Nearby BookDrop its own section in Integrations, closes #6360 by @chrox in https://github.com/readest/readest/pull/6499
* fix(ios): keep swipe brightness in sync with the system brightness, closes #6374 by @chrox in https://github.com/readest/readest/pull/6502
* feat(android): probe Hanvon eink service for full refresh by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6505
* fix(reader): animate page turns for PDF and comics on Windows and Linux, closes #6380 by @chrox in https://github.com/readest/readest/pull/6506
* fix(reader): stop the sidebar-width flash on Windows and Linux page turns by @chrox in https://github.com/readest/readest/pull/6509
* feat(annotator): edit highlight ranges and notes inside footnote popups, closes #6504 by @chrox in https://github.com/readest/readest/pull/6510
* fix(reader): keep the selected word readable in dark mode, closes #6503 by @chrox in https://github.com/readest/readest/pull/6512
* fix(annotator): open imported highlights on tap, closes #6160 by @chrox in https://github.com/readest/readest/pull/6515
* fix(annotator): keep the highlight toolbar off the footnote popup, closes #6390 by @chrox in https://github.com/readest/readest/pull/6514
* feat(reader): show Duokan slim covers on tall mobile screens, closes #6513 by @chrox in https://github.com/readest/readest/pull/6516
* feat(reader): optionally mark italic text in dialogue highlighting, closes #6517 by @chrox in https://github.com/readest/readest/pull/6522
* fix(ios): keep chrome and page content clear of iPhone Duo's side status strip by @kad-air in https://github.com/readest/readest/pull/6312
* chore(deps): bump the github-actions group with 3 updates by @dependabot[bot] in https://github.com/readest/readest/pull/6523
* feat(layout): Column Gap setting for two-column spreads by @kad-air in https://github.com/readest/readest/pull/6507
* fix(ios): hide the status bar through the view controller for Xcode 27 builds by @kad-air in https://github.com/readest/readest/pull/6508
* fix(android): focus the WebView on cold start so the first page-turn key isn't lost by @RedHatter in https://github.com/readest/readest/pull/6519
* feat(widget): currently reading Android widget and widget options by @RedHatter in https://github.com/readest/readest/pull/6518
* fix(pdf): stop huge scanned pages crashing or blanking the reader on iOS, closes #6521 by @chrox in https://github.com/readest/readest/pull/6526
* feat(android): automatic e-ink full refresh every N page turns by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6525
* feat(sync): sync reading progress to Pagebound, closes #6511 by @chrox in https://github.com/readest/readest/pull/6528
* fix(reader): show Hardcover status on the sync row and push on tap by @RedHatter in https://github.com/readest/readest/pull/6527
* feat(windows): PDF thumbnails and Explorer preview pane, closes #6524 by @chrox in https://github.com/readest/readest/pull/6533
* feat(dictionary): look up Wiktionary in the book language's own edition, closes #6529 by @chrox in https://github.com/readest/readest/pull/6534
* fix(settings): align the BookOrbit sync rows with the rest of the card by @chrox in https://github.com/readest/readest/pull/6535
* fix(library): erase cloud progress and notes when purging reading data, closes #6532 by @chrox in https://github.com/readest/readest/pull/6536
* fix(epub): show whole pages of comics with unsized SVG page images by @chrox in https://github.com/readest/readest/pull/6537
* fix(bookorbit): list unmatched books for linking when only progress or stats sync is on by @chrox in https://github.com/readest/readest/pull/6539
* fix(calibre): push custom columns in the shape bookshelf filters read by @chrox in https://github.com/readest/readest/pull/6538
* fix(reader): remove note bubbles when deleting highlights by @kelvinalfaro in https://github.com/readest/readest/pull/6545
* fix(windows): stop the main window from growing on every launch by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6546
* feat(pdf): smooth theme colors and smart invert for PDFs by @chrox in https://github.com/readest/readest/pull/6550
* fix(notes): keep note edits from losing to the synced copy they change, closes #6544 by @chrox in https://github.com/readest/readest/pull/6551
* feat(crosspoint): Readest plugin for CrossPoint e-readers by @chrox in https://github.com/readest/readest/pull/6547
* chore(agent): update agent memories by @chrox in https://github.com/readest/readest/pull/6554
* feat(reader): turn PDF pages with the mouse wheel in Fit Width mode by @chrox in https://github.com/readest/readest/pull/6555
* feat(reader): show PDF page thumbnails in the TOC, closes #6177 by @chrox in https://github.com/readest/readest/pull/6553
* fix(reader): keep PDF selections from jumping across text gaps, closes #5599, closes #4945 by @chrox in https://github.com/readest/readest/pull/6559
* feat(crosspoint): web-only sign-in, in-app linking, and recently read books first by @chrox in https://github.com/readest/readest/pull/6561
* fix(reader): drop the horizontal scrollbar from fit-width PDFs by @chrox in https://github.com/readest/readest/pull/6560
* fix(reader): stop the page container's fade on e-ink panels by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6565
* fix(audiobookshelf): fetch a synced audiobook's cover before shelving it by @chrox in https://github.com/readest/readest/pull/6564
* feat(reader): copy and save book images from one right-click menu by @chrox in https://github.com/readest/readest/pull/6567
* fix(reader): keep a selection from jumping next to a footnote marker, closes #6566 by @chrox in https://github.com/readest/readest/pull/6569
* fix(crosspoint): paint /link in the user's theme by @chrox in https://github.com/readest/readest/pull/6570
* fix(reader): stop annotation cards expanding while scrolling on iOS, closes #6568 by @chrox in https://github.com/readest/readest/pull/6571
* fix(utils): treat Korean as CJK in getLanguageInfo by @sx4im in https://github.com/readest/readest/pull/6572
* fix(deps): resolve open Dependabot alerts by @chrox in https://github.com/readest/readest/pull/6573
* fix(reader): set plain-text footnotes in the reader font by @kelvinalfaro in https://github.com/readest/readest/pull/6575
* fix(reader): keep a linked footnote's font in its popup, closes #3602 by @chrox in https://github.com/readest/readest/pull/6580
* docs(readme): serve the Ask DeepWiki badge from shields.io by @chrox in https://github.com/readest/readest/pull/6585
* fix(reader): smooth highlights on scanned PDFs and keep ones dragged past a page's end, closes #6578 by @chrox in https://github.com/readest/readest/pull/6581
* fix(reader): keep the e-ink battery percentage readable at any charge by @chrox in https://github.com/readest/readest/pull/6588
* feat(reader): edit a book's metadata from Book Details in the reader, closes #6584 by @chrox in https://github.com/readest/readest/pull/6587
* fix(reader): select and deselect in the clicked chapter at scroll-mode boundaries, closes #6583 by @chrox in https://github.com/readest/readest/pull/6591
* fix(reader): keep the dragged range when a PDF instant highlight runs past the page by @chrox in https://github.com/readest/readest/pull/6597
* fix(windows): stop the PDF preview pane from freezing Explorer, closes #6590 by @chrox in https://github.com/readest/readest/pull/6594
* feat(crosspoint): plugin updates, version display, and sync for optimized EPUBs by @chrox in https://github.com/readest/readest/pull/6592
* feat(translation): custom translation providers with a prompt library by @chrox in https://github.com/readest/readest/pull/6582
* fix(reader): remember where a locked, zoomed PDF page is panned across reopening by @chrox in https://github.com/readest/readest/pull/6595
* feat(shortcuts): bind several keys to one action, closes #6600 by @chrox in https://github.com/readest/readest/pull/6603
* feat(reader): open the image menu with a long press on iOS and Android, closes #6574 by @chrox in https://github.com/readest/readest/pull/6601
* fix(koplugin): stop BookDrop start errors popping up on every launch by @chrox in https://github.com/readest/readest/pull/6604
* feat(reader): show a PDF's header and footer only at the page's own edges, closes #6596 by @chrox in https://github.com/readest/readest/pull/6605
* fix(reader): keep pull-to-bookmark off the top screen edge, enable it on e-ink, and size the ribbon consistently, closes #6599 by @chrox in https://github.com/readest/readest/pull/6606
* fix(reader): return to the open book when leaving the account page, closes #6607 by @chrox in https://github.com/readest/readest/pull/6609
* fix(reader): reject backslash redirects and retry failed books on return by @chrox in https://github.com/readest/readest/pull/6610
* feat(dictionary): context dictionary, closes #5544 by @nphng15 in https://github.com/readest/readest/pull/5881
* fix(crosspoint): link an optimized copy to the book being read when duplicates tie by @chrox in https://github.com/readest/readest/pull/6614
* fix(sync): don't let a deleted copy's position pull a new copy forward by @chrox in https://github.com/readest/readest/pull/6615
* fix(reader): apply scroll overlap to fixed-layout books only; tidy the fixed-layout view menu by @chrox in https://github.com/readest/readest/pull/6621
* fix(windows): show the main window only after the themed page is painted by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6611
* fix(library): carousel cover spine, Rename Group, Import Books placement, reader return transition by @chrox in https://github.com/readest/readest/pull/6624
* fix(library): keep nested groups when renaming a group by @chrox in https://github.com/readest/readest/pull/6625
* feat(library): badge the series index on covers inside a series group by @kelvinalfaro in https://github.com/readest/readest/pull/6579
* fix(reader): keep scrolled PDFs smooth on iOS: virtualize the strip, hide PDF chrome by layout by @chrox in https://github.com/readest/readest/pull/6626
* feat(tts): sentence-by-sentence mode and A-B repeat by @chrox in https://github.com/readest/readest/pull/6627
* feat(hardcover): sign in with OAuth using the device authorization flow by @RedHatter in https://github.com/readest/readest/pull/6612
* fix(hardcover): follow API rate limits and batch journal writes by @RedHatter in https://github.com/readest/readest/pull/6617
* fix(dictionary): lift dark text colors in dark mode by @itsmunzir in https://github.com/readest/readest/pull/6622
* fix(widget): keep E-ink reading widget text legible in dark mode by @chrox in https://github.com/readest/readest/pull/6628
* feat(library): hide the bookshelf page buttons by default on e-ink by @chrox in https://github.com/readest/readest/pull/6631
* fix(reader): save library progress before the app quits (#6623) by @chrox in https://github.com/readest/readest/pull/6633
* chore(agent): update agent memories by @chrox in https://github.com/readest/readest/pull/6634
* fix(import): pick the declared cover when <meta name="cover"> holds an href by @chrox in https://github.com/readest/readest/pull/6635
* feat(hardcover): use the account's default visibility for new journal entries by @RedHatter in https://github.com/readest/readest/pull/6638
* fix(opds): load plain-http covers natively on iOS/macOS (#6637) by @chrox in https://github.com/readest/readest/pull/6639
* fix(library): keep the bookshelf column count while dragging a file in by @chrox in https://github.com/readest/readest/pull/6640
* fix(library): search book contents only within the opened group by @chrox in https://github.com/readest/readest/pull/6641
* fix(library): keep the shelf scroll position after opening a book by @chrox in https://github.com/readest/readest/pull/6642
* release: version 0.12.12 by @chrox in https://github.com/readest/readest/pull/6644

## New Contributors
* @hulkbig made their first contribution in https://github.com/readest/readest/pull/6369
* @WestXu made their first contribution in https://github.com/readest/readest/pull/6402
* @davidfvaquero made their first contribution in https://github.com/readest/readest/pull/6429
* @shiningsprk-arch made their first contribution in https://github.com/readest/readest/pull/6406
* @itsmunzir made their first contribution in https://github.com/readest/readest/pull/6434
* @RedHatter made their first contribution in https://github.com/readest/readest/pull/6430
* @stantonb made their first contribution in https://github.com/readest/readest/pull/6441
* @sx4im made their first contribution in https://github.com/readest/readest/pull/6572
* @nphng15 made their first contribution in https://github.com/readest/readest/pull/5881

**Full Changelog**: https://github.com/readest/readest/compare/v0.12.10...v0.12.12

# v0.12.10 · 2026-09-21

## Release Highlights
* Library: You can now organize books into configurable bookshelves, tag books in bulk
* Audiobooks: You can download Audiobookshelf books for offline listening, stream audiobooks from OPDS catalogs and BookOrbit
* Reading: You can now open HTML files as books, and select, highlight, and look up text in Paragraph Mode
* Sync: Reading progress refreshes when you return to the app, WebDAV sync is more reliable, and Readwise exports now include bookmarks
* TTS: You can now browse and resume your books from Android Auto and pick up recent books from CarPlay
* PDF: Page-turn animations now work on PDFs, comics, and fixed-layout books, and wide comic pages get a spread of their own
* KOReader: Added background sync, group downloads, and more library controls, and highlights you delete stay deleted
* Dictionary: Pronunciations can play automatically on lookup, accented words are easier to find
* More: Backups are much faster and keep the screen awake, and fixed freezes on App launch and in image-heavy chapters

## What's Changed
* release: version 0.12.8 by @chrox in https://github.com/readest/readest/pull/6135
* fix(library): keep the context menu actions wired to their items by @chrox in https://github.com/readest/readest/pull/6143
* fix(reader): draw the selection toolbar above the footnote popup by @chrox in https://github.com/readest/readest/pull/6146
* fix(ci): bundle libxkbcommon-x11 in the CEF AppImage by @chrox in https://github.com/readest/readest/pull/6151
* fix(proofread): keep selection rules applied after a toggle, edit or reopen (#6148) by @chrox in https://github.com/readest/readest/pull/6152
* chore(deps): bump the github-actions group with 3 updates by @dependabot[bot] in https://github.com/readest/readest/pull/6166
* fix(txt): detect Chinese chapters numbered with 两 or uppercase numerals (#6172) by @chrox in https://github.com/readest/readest/pull/6181
* fix(annotator): keep a highlight's rounded caps on its own page, closes #6128 by @chrox in https://github.com/readest/readest/pull/6182
* feat(reader): hide the image viewer controls on tap by @chrox in https://github.com/readest/readest/pull/6183
* Fixed translation error by @tygoee in https://github.com/readest/readest/pull/6215
* fix(reader): keep sliders mirrored when a book turns the layout RTL by @jadhavgaurav in https://github.com/readest/readest/pull/6168
* docker: pull minio images from quay.io, Docker Hub removed them by @thietala in https://github.com/readest/readest/pull/6196
* fix(payment): resolve the user's plan across every billing provider by @chrox in https://github.com/readest/readest/pull/6228
* fix(reader): open image-heavy sections in paged mode without freezing by @chrox in https://github.com/readest/readest/pull/6229
* fix(linux): drop the WebKitGTK assumptions now that Linux is CEF only by @Berserker-GM in https://github.com/readest/readest/pull/6218
* chore(deps): bump the github-actions group with 5 updates by @dependabot[bot] in https://github.com/readest/readest/pull/6236
* ci(android): stop asking sdkmanager for the removed `tools` package by @chrox in https://github.com/readest/readest/pull/6238
* Fix page-turn direction fallback and add missing applyMarginAndGap for vertical layout by @JackyHe398 in https://github.com/readest/readest/pull/6197
* fix(opds): persist sync progress incrementally so a large first sync can converge by @raman325 in https://github.com/readest/readest/pull/6237
* fix(android): stop the app freezing at launch on a page load deadlock by @chrox in https://github.com/readest/readest/pull/6240
* test(paginator): wait for the scroll relocate in the scrolled cover test by @chrox in https://github.com/readest/readest/pull/6243
* chore(agent): update agent memories by @chrox in https://github.com/readest/readest/pull/6244
* fix(epub): play embedded media the OPF manifest never declares by @chrox in https://github.com/readest/readest/pull/6245
* feat(reader): animate page turns on PDF, CBZ and fixed-layout books by @chrox in https://github.com/readest/readest/pull/6246
* fix(tts): keep a non-English book on its own voice when the doc says en-US by @chrox in https://github.com/readest/readest/pull/6247
* fix(reader): select text on a long press near a link on Android (#6242) by @chrox in https://github.com/readest/readest/pull/6248
* fix(paginator): keep an RTL book's progression when a re-render lands mid-load by @chrox in https://github.com/readest/readest/pull/6249
* fix(reader): backward page curl on PDF/CBZ froze a few pixels in by @chrox in https://github.com/readest/readest/pull/6250
* feat(reader): animate Push on PDF, CBZ and fixed-layout books by @chrox in https://github.com/readest/readest/pull/6251
* fix(reader): keep a page-wide image inside its column in paginated mode by @chrox in https://github.com/readest/readest/pull/6252
* fix(macos): keep the traffic lights on the library page and stop them jumping on navigation by @chrox in https://github.com/readest/readest/pull/6253
* feat(reader): confirm before following external links by @chrox in https://github.com/readest/readest/pull/6254
* fix(ios): restore cross-page selection on iPadOS 27 by @chrox in https://github.com/readest/readest/pull/6255
* fix(reader): let the macOS annotation export save to disk (#6201) by @chrox in https://github.com/readest/readest/pull/6260
* feat(reader): select, highlight and look up text in Paragraph Mode by @chrox in https://github.com/readest/readest/pull/6258
* fix(ios): keep reader screen awake with native idle timer by @chrox in https://github.com/readest/readest/pull/6261
* fix(reader): restore tablet toolbar taps at fractional display density by @chrox in https://github.com/readest/readest/pull/6263
* feat(audiobookshelf): sync reading progress for ebook-only books (#6257) by @chrox in https://github.com/readest/readest/pull/6264
* feat(audiobookshelf): download books for offline use and import ABS zips from the web browser by @chrox in https://github.com/readest/readest/pull/6267
* fix(abs): stream audiobook tracks through a loopback media proxy so self-signed servers play (#6216) by @chrox in https://github.com/readest/readest/pull/6268
* fix(annotator): hand the selection back when the instant dictionary closes by @chrox in https://github.com/readest/readest/pull/6272
* perf(reader): split chapter loading to reduce swipe stalls by @chrox in https://github.com/readest/readest/pull/6266
* feat(reader): give each wide comic page a spread of its own (#6210) by @chrox in https://github.com/readest/readest/pull/6273
* fix(reader): preserve style tag attributes in the style transformer by @jadhavgaurav in https://github.com/readest/readest/pull/6270
* fix(nix): add imagesize to the CEF lockfile by @chrox in https://github.com/readest/readest/pull/6274
* feat(reader): cache wide comic pages and find them in streamed comics (#6210) by @chrox in https://github.com/readest/readest/pull/6276
* fix(bookdrop): only sound on a completed transfer, enable Nearby BookDrop by default by @chrox in https://github.com/readest/readest/pull/6277
* feat(reader): add pull-down bookmark gesture setting by @chrox in https://github.com/readest/readest/pull/6278
* fix(sentry,about): report the real WebView build via webview_version() by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6275
* test(bookdrop): make the cue test independent of test order by @chrox in https://github.com/readest/readest/pull/6279
* feat(reader): import and render HTML files, closes #6198 by @chrox in https://github.com/readest/readest/pull/6281
* feat(dictionary): auto-play pronunciation on lookup by @chrox in https://github.com/readest/readest/pull/6280
* fix(nix): don't query wry's webview_version on Linux by @chrox in https://github.com/readest/readest/pull/6282
* feat(readwise): export bookmarks and their notes by @chrox in https://github.com/readest/readest/pull/6294
* fix(android): recognize iReader devices in e-ink detection by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6293
* fix(backup): keep the screen awake and move bulk zip work to Rust, closes #6291 by @chrox in https://github.com/readest/readest/pull/6299
* fix(translate): remember source language per book by @chrox in https://github.com/readest/readest/pull/6300
* feat(wordlens): Traditional Chinese hints and an English→Arabic pack by @chrox in https://github.com/readest/readest/pull/6303
* fix(test): stop ResizeObserver notices flooding the browser-test log by @chrox in https://github.com/readest/readest/pull/6305
* fix(linux): explain missing X11 display on startup by @chrox in https://github.com/readest/readest/pull/6302
* feat(android): browse and resume books in Android Auto by @kelvinalfaro in https://github.com/readest/readest/pull/6285
* feat(opds): stream audiobooks from OPDS catalogs, with a BookOrbit connector (#6224) by @chrox in https://github.com/readest/readest/pull/6301
* fix(reader): keep highlight options inside the reading area by @chrox in https://github.com/readest/readest/pull/6306
* chore(agent): update agent memories by @chrox in https://github.com/readest/readest/pull/6309
* feat(audiobook): stream BookOrbit audio through the loopback media proxy (#6224) by @chrox in https://github.com/readest/readest/pull/6308
* fix(sync): retry failed WebDAV writes without advancing config state by @chrox in https://github.com/readest/readest/pull/6310
* fix(sync): preserve WebDAV errors and report incomplete syncs by @chrox in https://github.com/readest/readest/pull/6311
* fix(reader): prevent vertical toolbar swipes from paging Push books by @chrox in https://github.com/readest/readest/pull/6313
* fix(mobile): align reader menus and improve dialog dismissal by @chrox in https://github.com/readest/readest/pull/6314
* fix(translate): decode HTML entities in popup text by @chrox in https://github.com/readest/readest/pull/6317
* fix: correct remaining-time sorting and chapter estimates by @chrox in https://github.com/readest/readest/pull/6319
* fix(dictionary): normalize Unicode and fold Latin diacritics by @chrox in https://github.com/readest/readest/pull/6320
* feat(koreader): background sync, group downloads, and library controls by @chrox in https://github.com/readest/readest/pull/6321
* fix(koreader): keep synced highlight deletions from reappearing by @chrox in https://github.com/readest/readest/pull/6322
* fix: refresh sidebar note timestamps every minute by @kv-chiu in https://github.com/readest/readest/pull/6324
* feat(library): add configurable bookshelves by @chrox in https://github.com/readest/readest/pull/6329
* fix(library): improve e-ink pagination and bookshelf sync by @chrox in https://github.com/readest/readest/pull/6330
* fix(reader): keep note editors open until saving succeeds by @chrox in https://github.com/readest/readest/pull/6331
* fix(sync): refresh reading progress when the app resumes by @chrox in https://github.com/readest/readest/pull/6332
* fix(reader): read M4B chapters when moov comes after the audio (#6262) by @knigam in https://github.com/readest/readest/pull/6327
* feat(library): book tags in the list view and a Tag Books action by @chrox in https://github.com/readest/readest/pull/6334
* fix(ui): smooth bottom-sheet gestures and Settings scrolling by @chrox in https://github.com/readest/readest/pull/6335
* fix(library): prevent scrollbar initialization layout shift by @chrox in https://github.com/readest/readest/pull/6336
* chore(payments): end the Full Customization grace period for storage add-ons by @chrox in https://github.com/readest/readest/pull/6337
* fix(reader): size annotation toolbar to enabled actions by @chrox in https://github.com/readest/readest/pull/6338
* fix(payments): store Play cancellation time as a timestamp by @chrox in https://github.com/readest/readest/pull/6342
* feat(ios): add CarPlay recent books and fix scene handoff by @chrox in https://github.com/readest/readest/pull/6339
* fix: harden ebook content and proxy trust boundaries by @chrox in https://github.com/readest/readest/pull/6343
* fix(tts): bound startup probes and filter Apple system voices by @chrox in https://github.com/readest/readest/pull/6345
* fix(android-auto): play cold EPUBs in media service by @kelvinalfaro in https://github.com/readest/readest/pull/6341
* fix: align player headers and restore mobile view menu dismissal by @chrox in https://github.com/readest/readest/pull/6346
* chore(agent): update agent memories by @chrox in https://github.com/readest/readest/pull/6348
* release: version 0.12.10 by @chrox in https://github.com/readest/readest/pull/6349

## New Contributors
* @tygoee made their first contribution in https://github.com/readest/readest/pull/6215
* @thietala made their first contribution in https://github.com/readest/readest/pull/6196
* @Berserker-GM made their first contribution in https://github.com/readest/readest/pull/6218
* @JackyHe398 made their first contribution in https://github.com/readest/readest/pull/6197
* @raman325 made their first contribution in https://github.com/readest/readest/pull/6237
* @kelvinalfaro made their first contribution in https://github.com/readest/readest/pull/6285
* @kv-chiu made their first contribution in https://github.com/readest/readest/pull/6324
* @knigam made their first contribution in https://github.com/readest/readest/pull/6327

**Full Changelog**: https://github.com/readest/readest/compare/v0.12.8...v0.12.10

# v0.12.8 · 2026-09-07

## Release Highlights
* Reading: Customize the information shown in headers and footers, resize text with zoom shortcuts
* Sync: You can choose whether to use Readest Cloud before signing in, and recover missing covers during sync
* Annotations: You can now import highlights, bookmarks, and reading progress from ReadEra, and sync your notes and highlights to Notion
* Audiobooks: You can now stream ebook-only titles from Audiobookshelf
* Text-to-Speech: use Apple Enhanced and Premium voices on the web, and optionally skip parenthetical readings in Japanese books
* Web Imports: You can now clip signed-in pages and import web novels that require an account, with more reliable text decoding
* Styling: Your library and reader can now use separate theme modes and colors, and e-ink mode is available on every platform
* PDF: You can lock horizontal panning while zoomed, highlights stay visible in dark mode, and PDFs work on older devices
* Dictionary: Dictionary entries can now play embedded audio, jump to parts of speech, and enlarge images
* Sharing: Nearby BookDrop now offers easier pairing, transfer sounds, and more reliable device discovery and reconnection

## What's Changed
* fix(ios): stop web-browser downloads from deadlocking the main thread by @chrox in https://github.com/readest/readest/pull/5947
* feat(settings): show which scope the Settings dialog writes by @bmfrosty in https://github.com/readest/readest/pull/5933
* feat(ui): separate theme mode and color for the library and the reader by @chrox in https://github.com/readest/readest/pull/5948
* fix(reader): stop a mid-touch text selection from hijacking the brightness swipe (#5939) by @chrox in https://github.com/readest/readest/pull/5958
* feat(reader): customizable header and footer style (#5938) by @chrox in https://github.com/readest/readest/pull/5960
* fix(reader): contain Notebook text while typing (#5956) by @chrox in https://github.com/readest/readest/pull/5962
* fix(library): update the existing book when an updated EPUB is re-imported (#5959) by @chrox in https://github.com/readest/readest/pull/5961
* feat(grouping): Adding existing status as Grouping by @rigen1048 in https://github.com/readest/readest/pull/5935
* fix(reader): keep TTS chapter indicators synced (#5953) by @chrox in https://github.com/readest/readest/pull/5968
* fix(reader): correct PDF reference totals and slider endpoint (#5951) by @chrox in https://github.com/readest/readest/pull/5969
* feat(notion): sync notes and highlights to Notion by @PaleVerge in https://github.com/readest/readest/pull/5949
* fix(reader): stabilize Hardcover Sync submenu sizing by @chrox in https://github.com/readest/readest/pull/5978
* fix(reader): shrink hidden Android navigation controls (#5966) by @chrox in https://github.com/readest/readest/pull/5974
* fix(markdown): support tab-indented footnotes by @chrox in https://github.com/readest/readest/pull/5975
* chore: update agent memories and tidy library styles by @chrox in https://github.com/readest/readest/pull/5985
* feat(payments): yearly subscription plans and a modernized store front by @chrox in https://github.com/readest/readest/pull/5989
* feat(payments): record Apple one-time purchases from ONE_TIME_CHARGE by @chrox in https://github.com/readest/readest/pull/5993
* fix(payments): acknowledge Apple notifications that carry no transaction by @chrox in https://github.com/readest/readest/pull/5994
* feat(payments): separate storage and customization entitlements, unlock all when self-hosted by @chrox in https://github.com/readest/readest/pull/5996
* fix(payments): align the plan panels and stop the header eating clicks by @chrox in https://github.com/readest/readest/pull/6000
* READ-9: shrink hidden Android navigation buttons to 8px by @chrox in https://github.com/readest/readest/pull/6001
* fix(bookorbit): cap page-stat uploads at server limits by @chrox in https://github.com/readest/readest/pull/6002
* fix(reader): stop the note popup growing scrollbars of its own by @chrox in https://github.com/readest/readest/pull/6006
* fix(opds): import the publication date, not the calibre added-date by @chrox in https://github.com/readest/readest/pull/6008
* fix(kosync): resolve KOReader XPointers in their own DocFragment by @chrox in https://github.com/readest/readest/pull/6014
* fix(reader): write a new note on the selection, not in the sidebar by @chrox in https://github.com/readest/readest/pull/6013
* fix(pdf): render documents on older WebKit by @chrox in https://github.com/readest/readest/pull/6019
* fix(dict): play MDD audio, jump to POS sections, zoom entry images by @chrox in https://github.com/readest/readest/pull/6021
* fix(reader): keep lookup surfaces open when native handles are suppressed by @chrox in https://github.com/readest/readest/pull/6022
* feat(bookdrop): AirDrop-style Nearby BookDrop with pairing, sounds, and resilient discovery by @chrox in https://github.com/readest/readest/pull/6023
* feat(settings): add a Gamepad Support toggle by @chrox in https://github.com/readest/readest/pull/6027
* feat(pdf): add a Lock Horizontal Panning toggle for zoomed pages by @chrox in https://github.com/readest/readest/pull/6030
* feat(annotator): show highlight options immediately when highlight tool is present by @chrox in https://github.com/readest/readest/pull/6031
* fix(sync): fit OAuth tokens in Windows keychain by @chrox in https://github.com/readest/readest/pull/6033
* feat(annotator): import highlights, bookmarks and progress from ReadEra by @chrox in https://github.com/readest/readest/pull/6032
* feat(sync): add a manual sync option for BookOrbit (#6029) by @chrox in https://github.com/readest/readest/pull/6034
* fix(reader): keep mobile header tools stationary by @chrox in https://github.com/readest/readest/pull/6035
* fix(annotator): keep the annotation toolbar below the range handles by @chrox in https://github.com/readest/readest/pull/6036
* chore: update agent memories by @chrox in https://github.com/readest/readest/pull/6037
* fix(reader): restore XHTML namespaces so book CSS selectors match by @chrox in https://github.com/readest/readest/pull/6040
* fix(reader): draw scripted canvases and keep them inside their column by @chrox in https://github.com/readest/readest/pull/6042
* feat(sync): choose Readest Cloud before sign-in starts syncing by @chrox in https://github.com/readest/readest/pull/6045
* chore(deps): bump the github-actions group with 5 updates by @dependabot[bot] in https://github.com/readest/readest/pull/6039
* fix(ui): preserve mobile toast gutters by @chrox in https://github.com/readest/readest/pull/6046
* fix(bookdrop): recover the iOS service after suspension and keep peer presence honest by @chrox in https://github.com/readest/readest/pull/6049
* fix(koplugin): honour BookDrop goodbyes and un-dangle the localsend pin by @chrox in https://github.com/readest/readest/pull/6050
* fix(novel): decode imported pages with the charset they declare by @chrox in https://github.com/readest/readest/pull/6052
* fix(audiobookshelf): add web CORS setup hint by @chrox in https://github.com/readest/readest/pull/6053
* fix(reader): restore EPUB namespace in section fragments by @chrox in https://github.com/readest/readest/pull/6054
* fix(reader): stop the default font from overriding a book's embedded fonts by @k6G52m4Dz75W in https://github.com/readest/readest/pull/6047
* fix(reader): make the reading ruler legible on e-ink by @chrox in https://github.com/readest/readest/pull/6055
* feat(tts): skip inline parenthetical readings by @chrox in https://github.com/readest/readest/pull/6057
* fix(tts): stop Android narration rewinding when the block cursor stalls by @chrox in https://github.com/readest/readest/pull/6058
* feat(audiobookshelf): stream ebook-only books by @chrox in https://github.com/readest/readest/pull/6056
* fix(annotator): stop PDF selections opening the translator popup by @chrox in https://github.com/readest/readest/pull/6063
* chore(agent): update agent memories by @chrox in https://github.com/readest/readest/pull/6064
* fix: resolve dependency and code-scanning alerts by @chrox in https://github.com/readest/readest/pull/6065
* fix(annotator): keep PDF highlights visible in dark mode by @chrox in https://github.com/readest/readest/pull/6066
* feat(reader): zoom shortcuts adjust font size in reflowable books, closes #5694 by @chrox in https://github.com/readest/readest/pull/6067
* fix(annotator): anchor the selection toolbar to the book cell by @chrox in https://github.com/readest/readest/pull/6068
* fix: own route transitions and scope Yandex cancellation by @chrox in https://github.com/readest/readest/pull/6069
* fix: guard reader reloads, search views, and sentence navigation by @chrox in https://github.com/readest/readest/pull/6070
* fix: await PDF destinations for TTS download chapters by @chrox in https://github.com/readest/readest/pull/6072
* fix: skip desktop fullscreen commands on mobile by @chrox in https://github.com/readest/readest/pull/6073
* fix(tts): read aloud only the selection on Ctrl/Cmd+R by @chrox in https://github.com/readest/readest/pull/6076
* fix(tts): stop a redundant PDF render detaching the ranges TTS reads by @chrox in https://github.com/readest/readest/pull/6075
* fix: ignore incomplete reader relocation events after close by @chrox in https://github.com/readest/readest/pull/6077
* feat(linux): ship Readest on the tauri CEF runtime by @chrox in https://github.com/readest/readest/pull/6074
* fix(linux): catch the CEF stack up with upstream feat/cef by @chrox in https://github.com/readest/readest/pull/6080
* fix: serialize TTS cache compaction before shutdown by @chrox in https://github.com/readest/readest/pull/6078
* chore: bump tauri to version 2.11.5 by @chrox in https://github.com/readest/readest/pull/6081
* feat(nix): build the Linux package on the CEF runtime by @chrox in https://github.com/readest/readest/pull/6083
* fix(nix): let the linker resolve libcef.so's own dependencies by @chrox in https://github.com/readest/readest/pull/6084
* chore: remove the packages/tao submodule by @chrox in https://github.com/readest/readest/pull/6085
* feat(linux): debug the CEF build over CDP, and three fixes it found by @chrox in https://github.com/readest/readest/pull/6087
* fix: continue library sync after cover download failures by @chrox in https://github.com/readest/readest/pull/6086
* fix(epub): match `[xml|lang]` and `:lang()` on `xml:lang` attributes by @chrox in https://github.com/readest/readest/pull/6090
* feat(ui): dismiss bottom sheets by swiping down from anywhere by @chrox in https://github.com/readest/readest/pull/6097
* fix(tts): allow Apple Enhanced and Premium Web TTS voices by @chrox in https://github.com/readest/readest/pull/6099
* fix(docker): unbreak large uploads and self-hosted cloud sync by @chrox in https://github.com/readest/readest/pull/6100
* fix(ci): bundle the NSS modules the CEF AppImage dlopens by @chrox in https://github.com/readest/readest/pull/6101
* Fix Wayland WebKitGTK window sizing bug on non-CEF Linux builds by @Frebbers in https://github.com/readest/readest/pull/6098
* fix(reader): never let the hidden nav buttons take taps by @chrox in https://github.com/readest/readest/pull/6102
* fix(ui): pad the plans section so its buttons align on mobile by @chrox in https://github.com/readest/readest/pull/6103
* feat(reader): hinge the two-column Page Curl at the spine by @kad-air in https://github.com/readest/readest/pull/6107
* fix(ci): bundle the audio libraries the CEF AppImage dlopens by @chrox in https://github.com/readest/readest/pull/6108
* fix(test): keep the curl leaf in flight until the incoming bitmap lands by @chrox in https://github.com/readest/readest/pull/6114
* feat(ui): remove e-ink mode checks for all devices and platforms by @54wedge in https://github.com/readest/readest/pull/6113
* ci: manual Linux AppImage build for validating bundler changes by @chrox in https://github.com/readest/readest/pull/6115
* feat: unify web imports with signed-in page clipping by @chrox in https://github.com/readest/readest/pull/6117
* feat(proofread): allow tts rules to be created in proofread management panel by @54wedge in https://github.com/readest/readest/pull/6109
* fix(deeplink): consume the launch URL once per app run by @chrox in https://github.com/readest/readest/pull/6111
* fix(tts): keep mini player above navigation panels by @chrox in https://github.com/readest/readest/pull/6118
* fix(sync): repair missing local covers from the file-sync remote by @jadhavgaurav in https://github.com/readest/readest/pull/6116
* compat(image): exclude some images in gallery view by @54wedge in https://github.com/readest/readest/pull/6120
* chore(scripts): account inspector and merge scripts for support tickets by @chrox in https://github.com/readest/readest/pull/6121
* feat: support authenticated web novel imports by @chrox in https://github.com/readest/readest/pull/6119
* fix(sync): closing unclosed void tags before XML re-parsing, closes #5271 by @chrox in https://github.com/readest/readest/pull/6122
* fix(ci): use CEF bundler with deployment array quoting fix by @chrox in https://github.com/readest/readest/pull/6125
* fix(nix): sync CEF dependencies for offline builds by @chrox in https://github.com/readest/readest/pull/6126
* release: version 0.12.8 by @chrox in https://github.com/readest/readest/pull/6127
* fix(reader): sync reading progress on a first open in scrolled mode by @chrox in https://github.com/readest/readest/pull/6130
* fix(android): follow system theme in reading widget by @chrox in https://github.com/readest/readest/pull/6131
* fix(abs): refresh cached token for streaming file access by @chrox in https://github.com/readest/readest/pull/6132
* i18n: update translations by @chrox in https://github.com/readest/readest/pull/6134

## New Contributors
* @bmfrosty made their first contribution in https://github.com/readest/readest/pull/5933
* @rigen1048 made their first contribution in https://github.com/readest/readest/pull/5935
* @PaleVerge made their first contribution in https://github.com/readest/readest/pull/5949
* @k6G52m4Dz75W made their first contribution in https://github.com/readest/readest/pull/6047
* @Frebbers made their first contribution in https://github.com/readest/readest/pull/6098
* @kad-air made their first contribution in https://github.com/readest/readest/pull/6107

**Full Changelog**: https://github.com/readest/readest/compare/v0.12.6...v0.12.8
