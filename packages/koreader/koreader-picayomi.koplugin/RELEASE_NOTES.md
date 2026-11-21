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

# v1.6.3 · 2026-11-20

### 中文

- 黑白阅读时，部分原先因内存不足而打不开的大幅渐进式 JPEG 漫画现在可以按原图清晰度显示，无需切换缩略图。

### English

- In grayscale reading, some large progressive JPEG comic pages that previously ran out of memory can now open at their original resolution without switching to thumbnails.

# v1.6.2 · 2026-11-19

### 中文

- 唤醒或重新联网后，源订阅自动检查遇到短暂网络故障时会稍后重试一次，减少刚亮屏就出现的失败提示。
- 减少退出漫画时的缓存写入，缩短返回上一页的等待。

### English

- Automatic source checks retry once after a temporary network failure on wake or reconnection, reducing error messages just after wake-up.
- Reduced cache writes when closing a comic so you can return to the previous screen sooner.

# v1.6.1 · 2026-11-19

### 中文

- 修复取消聚合搜索后仍可能向下一个来源发出请求的问题。
- 减少聚合搜索翻查多页结果时的重复调度和清理。

### English

- Fixed an issue where cancelling a search across sources could still send a request to the next source.
- Reduced redundant work when searching through multiple pages of results across sources.
