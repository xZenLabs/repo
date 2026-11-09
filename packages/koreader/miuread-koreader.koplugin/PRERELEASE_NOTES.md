# v6.5.0-beta.28 · 2026-11-09

- 修复 beta.27 在 GitHub Actions 发布前回归测试中 `_local_comment_enabled` 未加入模拟插件环境导致的失败：测试调用真实方法，并分别验证未关联和已关联本地 EPUB 的翻页行为。
- 将本地 EPUB 关联、章节匹配、评论回复以及私人上传书籍空划线补充查询的离线回归正式加入 `release-beta` 发布前检查，避免新功能未经 CI 验证就发包。
- 保留 beta.27 的本地 EPUB 社区评论功能及 beta.26 的下载、阅读时间、精确进度、多设备同步；不改变实际业务协议，Schema 仍为 136。
- 微信读书私人上传书籍的接口返回、EPUB 正文标记点击和 Kindle/KOReader 真机行为仍需在线与设备验收。

# v6.5.0-beta.26 · 2026-11-07

- fix(readtime): aggregate E-Ink offline reports and preserve unsent time (#184)
- fix(readtime): reserve safe Web retries before dispatch
- fix(readtime): exclude inactive gaps from Web reading time

# v6.5.0-beta.25 · 2026-11-07

- 本次更新准备发布 MiuRead 6.5.0-beta.24，重点修复 EPUB 多级目录问题，并完善 GitHub Release 与 Issue 自动关联机制。

# v6.5.0-beta.24 · 2026-11-07

- perf(reader): skip toolbar state refresh when reader toolbar is disabled
- perf(store): use ZIP central directory for EPUB identity instead of 1.75MB read and unzip subprocesses
- perf(reader): gate WeRead-only and toolbar-only onReaderReady tasks on local books
- fix(lifecycle): avoid 18s rebuild candidate false positive on CloseDocument
- perf(store): bound settings_equal seen stack, deduplicate incremental flush pass, and skip clean native close flushes
- perf(reader): isolate plugin-mode native books from recent-read writes, idle transition timers, and eager thought link guard
- fix(readtime): allow time reports when rereading finished books (#183)
- fix(readtime): preserve Web report status and failure scope
- feat(readtime): include Web reports in opt-in diagnostics

# v6.5.0-beta.23 · 2026-11-02

- 最近阅读内嵌统计收窄至文字区约 37%，并保留左侧书籍资料的最小宽度；只调整卡片内部布局，不改变主页 hero 高度、下方快捷栏、书架比例和分页。
- 双统计来源之间加入独立间距，压缩各组标题/图标占位，微调星期与打卡圆点的垂直节奏；单来源模式保持紧凑并居中。
- 简介整体轻微下移，继续使用剩余宽高显示文本；明确区分真正的简介与译者/语言等元数据，无简介时提示“暂无简介”，点击真实简介仍可打开完整介绍。
- 微信读书统计的小图标由通用评论气泡换为参考微信读书应用标识的离线单色适配图，适合墨水屏显示；该图标不代表腾讯官方授权或合作。
- 本版不修改 Wi-Fi、断网提醒、精确进度、Web/E-Ink 阅读时间、下载与评论协议，也不新增主页统计模块。
