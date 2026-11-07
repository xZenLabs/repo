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

# v6.5.0-beta.20 · 2026-11-02

- 书架封面开关同时控制桌面最近阅读封面和书架网格；隐藏封面后保留原卡片和网格布局，并填充书籍文字信息。
- 插件模式增加共享的“显示书架封面”选项，切换后即时刷新觅阅桌面，不删除封面缓存。
- 主页阅读统计增加“显示大时钟”；隐藏后统计卡片填充可用高度。顶栏原有专用设置新增“时间”，每分钟局部刷新。
- Wi-Fi 网络列表高度随扫描数量收缩，保留原生分页，并将原生弹窗标记为模态以避开主页后台重绘；关闭后刷新主页。
- 插件模式书籍菜单新增“下载正文与公开想法”，复用桌面现有版本状态与下载处理，不改变评论抓取和正文协议。
- 继承 beta.19 Wi-Fi 重连及联网后安全同步恢复策略。
