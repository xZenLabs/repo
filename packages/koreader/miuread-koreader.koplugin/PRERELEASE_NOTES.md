# v6.5.0-beta.17 · 2026-10-31

- 将 Google Books、Open Library 的图书元数据 HTTP 429 冷却分别隔离到 `metadata-google`、`metadata-openlibrary` 作用域，避免写入微信读书沿用的 `global` 限流文件。
- 图书元数据请求遇到自身 429 立即停止并尝试另一来源（可用时），不在元数据任务中持续等待 300 秒；原有网络补全开关保持可用。
- 只修改 `network_metadata.lua` 和版本标识，保留 beta.16 的 EPUB 下载/即时 Web 补全、阅读进度/时间 Worker、云端保护及 beta.5 发布工作流。
- 已存在的旧版 `weread-rate-limit.json` 仍须自行到期；不会绕过真实的微信读书 429。

# v6.5.0-beta.16 · 2026-10-31

- 恢复 Web 原文获取与 EPUB 文本严格匹配的独立判断：EPUB 安装后同一任务立即逐章获取 Web 原文，正文过短、重复或不一致不会阻止可信 Web 原文缓存。
- 保留实际阅读位置的唯一坐标校验：Web 来源已缓存并不代表 EPUB/XPointer 精确映射成功，不绕过原有阅读进度写入保护。
- 新增来源证明记录（账号、章节 UID、版本和内容摘要），已确认 Web 原文优先复用；当前下载直接来自 Web 的章节无需在补全阶段重复联网。
- 进度分别展示 Web 已缓存、EPUB 正文对应已验证、未匹配和网络失败；仅对未能获取 Web 原文的章节记录补全失败。
- 同一下载任务恢复及下载管理手动重试优先处理失败章节，不从头重取已缓存章节。
- EPUB 安装、阅读时间、进度上传、Web/E-Ink 正文选择和 beta.5 GitHub Beta 发布工作流保持原有行为。

# v6.5.0-beta.12 · 2026-10-31

- 为已安装的旧版 EPUB 新增后台 Web 章节定位来源补全；逐章匹配，不修改原书或阅读进度。
- 支持已安装书籍的补全任务暂停、重新验证、取消，以及离线重试和账号隔离。
- 恢复 KOReader 原生锁屏独立选项、主页快捷栏长按层级菜单。
- 统一评论获取/更新入口；指定范围可选择刷新已有评论。
- 内测发布流程恢复到 v6.5.0-beta.5 原版，手动发布仅需版本号。

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
