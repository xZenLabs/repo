# v1.6.8 · 2026-11-25

### 中文

- 修复源状态发生冲突后，关闭更新失败提示仍反复弹出、无法退出首页的问题。

### English

- Fixed an update error that repeatedly reopened after dismissal and prevented leaving the home screen when source settings conflicted.

# v1.6.7 · 2026-11-22

### 中文

- 漫画慢页会先显示加载提示，回翻时可复用上一页；打开漫画时点击加载提示即可取消。
- 小说切章时显示下载和缓存进度，进度未知时显示滚动条，章节就绪后再提示打开阅读器。
- 打开已缓存的小说章节时减少重复读取，保留原来的阅读位置。
- 成功提示显示一秒；失败提示显示原因并标明“点击关闭”，方便读完再关闭。
- 恢复后，新版界面会将恢复按钮置灰。恢复到 1.6.6 时，旧版仍可再次点击恢复按钮，切回刚才使用的版本。

### English

- Slow manga pages show a loading indicator, and turning back can reuse the previous page. Tap the opening notice to cancel.
- Chapter changes show download and cache progress, with an animated bar when progress is unknown. The reader opening notice appears once the chapter is ready.
- Cached novel chapters open with fewer repeated reads while preserving your reading position.
- Success notices appear for one second. Error notices explain the problem and show a tap-to-close hint so you can dismiss them when ready.
- The new interface disables the restore button after a rollback. If you restore 1.6.6, its older interface still lets you use the button to switch back.

# v1.6.6 · 2026-11-22

### 中文

- 漫画单页加载较慢时仍会提前下载下一页。连续下载失败后会尝试恢复预取，翻过大图后也会重新判断下一页可用的内存。
- 点列表封面可放大查看，再点屏幕任意位置关闭。点标题仍可进入详情。
- 返回、关闭和更新失败等提示改为短暂显示，操作提前完成时立即收起返回提示。

### English

- Manga preloading continues after a slow page. The reader can resume preloading after consecutive download failures and reassesses available memory after you turn past a large image.
- Tap a list cover to enlarge it, then tap anywhere to close it. Tap the title to open details.
- Return, close, and update error notices now appear briefly. The return notice closes as soon as navigation finishes.

# v1.6.5 · 2026-11-21

### 中文

- 黑白阅读时，部分大型 JPEG 漫画页显示更快，在可用内存较少时也能直接打开。
- 翻页后若可用内存已经恢复，回翻时可以直接显示仍在缓存中的上一页。

### English

- Some large JPEG comic pages render faster in grayscale and can open with less available memory.
- When memory has already recovered after a page turn, turning back can immediately show the previous page if it is still cached.

# v1.6.4 · 2026-11-20

### 中文

- 黑白阅读大型渐进式 JPEG 漫画时，部分页面可减少重复解码，更快显示。
- 分页漫画卡顿期间连续点击同一方向时，同一批积压的点击只翻一页，减少意外跳页。
- 内存不足时，会跳过已确定无法完成的大图后台预处理，为当前页保留资源。
- 阅读漫画或小说章节时，避免 Readest 在打开或唤醒时自动拉取数据，以及在退出时为自动同步检查 Wi-Fi；仍可手动同步。

### English

- Some large progressive JPEG comic pages display faster in grayscale thanks to fewer repeated decodes.
- In paginated comics, repeated taps in the same direction that were queued together during a stall now turn just one page.
- When memory is low, background processing skips large pages that cannot fit, leaving resources for the current page.
- Readest now skips automatic pulls when opening or waking a comic or novel chapter and avoids checking Wi-Fi for automatic sync on exit. Manual sync remains available.
