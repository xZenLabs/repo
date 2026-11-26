# v6.5.0 · 2026-11-26

- fix: 修复 E-Ink 授权续期与优化交互层级 (#191, #192)
- 内核改造，全面切换为原生
- 无用内核删除
- 双向定位补丁

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
