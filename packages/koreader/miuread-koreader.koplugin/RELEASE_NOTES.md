# v6.4.1 · 2026-11-09

- perf(reader): skip toolbar state refresh when reader toolbar is disabled
- perf(store): use ZIP central directory for EPUB identity instead of 1.75MB read and unzip subprocesses
- perf(reader): gate WeRead-only and toolbar-only onReaderReady tasks on local books
- fix(lifecycle): avoid 18s rebuild candidate false positive on CloseDocument
- perf(store): bound settings_equal seen stack, deduplicate incremental flush pass, and skip clean native close flushes
- perf(reader): isolate plugin-mode native books from recent-read writes, idle transition timers, and eager thought link guard
- fix(readtime): allow time reports when rereading finished books (#183)
- fix(readtime): preserve Web report status and failure scope
- feat(readtime): include Web reports in opt-in diagnostics
- fix(readtime): aggregate E-Ink offline reports and preserve unsent time (#184)
- fix(readtime): reserve safe Web retries before dispatch
- fix(readtime): exclude inactive gaps from Web reading time
- 本次更新准备发布 MiuRead 6.5.0-beta.24，重点修复 EPUB 多级目录问题，并完善 GitHub Release 与 Issue 自动关联机制。
- 导入书籍评论获取/稳定性提升
- 测试流程修改

# v6.4.0 · 2026-11-02

- 优化最近阅读布局、嵌入阅读统计并完善书籍信息显示（beta.21–23）

# v6.3.9 · 2026-11-02

- 阅读时间进度冲突修复
- wifi连接路径改善
- 修复书架界面、Wi-Fi 显示及下载入口 (beta.20)

# v6.3.8 · 2026-10-31

- 修复时间同步智能切换
- 修复eink下载书籍坐标丢失
- 阅读进度修复
- 阅读进度稳定靶点，时间暂有问题
- 阅读进度/时间 稳定锚点
- 部分功能回归，可作为中段基线
- 美化回归，时间进度稳固
- 进度安全测试
- 进度/时间稳定
- 第三方元数据请求的限流隔离

# v6.3.5 · 2026-10-30

- feat(readtime): preserve complete offline reading-time upload implementation
- fix(readtime): adapt Web outbox to upstream and preserve close tails
- fix(readtime): preserve upstream Web reporting and isolate E-Ink outbox
- 修复弹窗空白和美化评论获取进度条
- 实现 Web/E-Ink 智能阅读时间同步与离线补传，修复授权和同步稳定性问题，并全面优化菜单交互逻辑及黑白 SVG 图标体系
- 整合优化阅读时间记录与同步、评论下载及下一章自动预载，统一主页快捷操作和多级菜单，并新增 KOReader 原生锁屏支持
- 修复评论菜单调整后导致的发布测试失败，完善版本验证，保留此前阅读时间、评论下载及界面优化
- 阅读进度修复
- 稳定性修复
- 打包流程修复
