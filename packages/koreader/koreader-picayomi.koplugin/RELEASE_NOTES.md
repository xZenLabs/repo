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

# v1.6.0 · 2026-11-16

### 中文

- 首次进入可一键安装内置订阅的漫画和小说源，也可选择稍后安装。
- 插件包不再附带源；订阅更新支持补齐未安装源及新增源。
- 新用户默认开启插件和源更新检查，保留已有设置。
- 安装结果区分新增与更新，改善更新提示在中断后的恢复。
- 减少源更新检查的重复计算，避免失效弹窗继续触发下载。
- 加快聚合搜索排序，改善主页收藏刷新与详情简介布局。

### English

- Install manga and novel sources from the built-in subscription on first entry, or choose Later.
- Source-free plugin packages; subscription updates include missing and newly added sources.
- Automatic update checks default to on for new users; existing settings are preserved.
- Installation results distinguish added sources from updates; interrupted update prompts can be offered again.
- Fewer repeated subscription checks, with stale dialogs prevented from starting downloads.
- Faster aggregate search ranking and improved favorites refresh and detail layout.

# v1.5.12 · 2026-11-14

### 中文

- 封面加载遇到暂时网络错误时自动补试，改善多个来源的偶发缺图。
- 修复自动恢复登录遇到响应异常后丢失保存凭据的问题。

### English

- Retry temporary cover-loading failures to reduce intermittent missing covers across sources.
- Keep saved credentials when automatic sign-in recovery encounters an unexpected response.
