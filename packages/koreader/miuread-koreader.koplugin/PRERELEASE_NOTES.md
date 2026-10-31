# v6.5.0-beta.5 · 2026-10-31

- Fix final reading-end snapshot losing its genuine page-event sequence between pending save and upload guard; leave guarded, unsent progress intact when no evidence of reading exists.
- Persist real page-event IDs across Reader/Home instances; merge durable event watermarks independently of cloud progress transaction sequence.
- Verify trusted Web chapter coordinates with a pragmatic ±100-unit same-chapter tolerance (not a claim of identical rendering pages). Reject unresolved zero coordinates and stale/missing post-POST timestamps.
- Keep reading-time session coordinate behavior, EInk/Web routing, source backfill, pending verification-first recovery and existing release workflows unchanged.
- Add beta.5 regression coverage for blocked-then-read upload, 76/101 co mismatches, cross-instance event merging, and safe verification.

# v6.5.0-beta.4 · 2026-10-31

- 修复真实翻页后被无坐标 ProgressFence 提前拦截的问题，保留精准坐标上传与云端回读验证
- 修复阅读事件序号回退与相同云端观察重复加锁；未知章节 UID 不再猜测跳转
- EInk/Web 混合下载后后台逐章补齐缺少的可信 Web 坐标缓存，不改写 EPUB
- Web 坐标任务尊重 429 冷却、退避、登录隔离与可恢复队列，避免重复抓取
- 区分云端文本定位成功和坐标精确验证成功；新增相关回归测试

# v6.5.0-beta.3 · 2026-10-31

- 修复时间同步智能切换

# v6.5.0-beta.2 · 2026-10-30

- 内测版本更新至 6.5.0-beta.2，功能内容与当前 beta 分支一致。

# v6.5.0-beta.1 · 2026-10-30

- 整合优化阅读时间记录与同步、评论下载及下一章自动预载，统一主页快捷操作和多级菜单，并新增 KOReader 原生锁屏支持
- 修复评论菜单调整后导致的发布测试失败，完善版本验证，保留此前阅读时间、评论下载及界面优化
- 阅读进度修复
- 稳定性修复
- 打包流程修复
