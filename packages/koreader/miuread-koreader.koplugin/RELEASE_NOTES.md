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

# v6.2.1 · 2026-10-29

- 评论下载提醒优化

# v6.2.0 · 2026-10-29

- 阅读时间同步优化与评论批量获取
- 阅读事件上报恢复和评论UI下载改善
- 修补打包逻辑
- 完善同步相关提醒

# v6.1.0 · 2026-10-28

- fix: share live Store across reader and home instances
- 优化扩展下载安装流程：优先识别 GitHub Release 正式安装包，新增 GitHub 中文社区下载通道、大文件断点续传、慢速网络容错与完整性校验；同时调整后台任务优先级，确保书籍/插件下载不会阻塞阅读进度、阅读时间和批注同步。
- 修复主页与阅读页旧设置互相覆盖导致本地书库路径丢失的问题；两处现在保持同一份实时设置，本地书库选择、扫描结果和设置变更即时一致，同时保留后台下载隔离与现有同步行为。
- 新增设备美化分类与 DashWallpaper 首页推荐，统一书籍封面、墨痕和 DashWallpaper 的锁屏切换。第三方壁纸支持直接安装并使用，DashWallpaper 会先成功生成壁纸再切换，失败时完整保留原锁屏。
- 修复阅读时长上报引起的周期性卡顿，降低设置文件写入与内存压力，同时完整保留 beta18 的同步精度、异常恢复与后台稳定性。
- 修复微信书架在无有效分组时被错误过滤为 0 本的问题，并新增大书架分组建议，提升书架稳定性与可用性。
- 新增微信读书在线评论点赞/取消点赞，并完善点赞状态、点赞数、登录失效与电子墨水屏刷新处理，同时完整保留 beta20 的书架修复和 beta19 的阅读性能优化。
- 复用微信读书连接，整本下载耗时下降约四分之一 (#73)
- 正式纳入微信读书下载连接复用优化，减少整本下载过程中重复 TCP/TLS 握手，同时保持非下载网络行为、同步精度与后台稳定性不变。
- fix: 减少主页、评论与退出阅读卡顿，修复刷新及导航保存边界 (#112)
- 复用阅读页上下文，整本下载耗时下降约五分之一 (#110)
- beta.25 收口同步失败闭环：主页统一为“已同步/同步中/同步失败”，支持进度、SAFE 阅读时间与批注一键重试；精确进度只以 chapter_uid + co 判定，percent 仅用于导航。
- beta.26 收口 #107/#111/#114，并加固 #115/#116：修复剪贴板 table、1%→100% 风险和 OPF 元数据污染，主页可恢复丢失的已生成书籍关联；长篇定位继续只以 chapter_uid+co 验收，重型下载持续低内存时自动保存断点并休眠。
- 5.9.0-beta.1：Cloud Mirror & Seamless Resume。开书自动按 verified anchor、序列与真实更新时间选择最新精确位置；定位完成前保护翻页，2.5 秒软超时可先读本机，晚到云端在用户已操作后不得突跳。微信书架默认云端顺序，读完状态与当前位置分离解析；自动云端定位必须通过 chapter_uid + co 精确验收，失败立即回滚，成功后 8 秒内可撤回。
- 5.9.0-beta.2：Cloud Mirror Stabilization。修正 latest-wins freshness：技术性本地快照不再伪造“刚刚更新”；明确更旧的晚到云端响应不会覆盖已知更新状态。书架与开书统一使用事件更新时间，并加固 Beta Release 的 CHANGELOG/回归校验。保留 beta.1 的自动续读、2.5 秒 fallback、晚到云端防突跳、8 秒撤回及 chapter_uid + co 精确验收。
- 5.9.0-beta.4：修复 5.9 自动续读的 position_state 循环引用崩溃和首次同步锚点误判；持久化位置改为纯标量快照并可启动自愈，remote_observed 不再冒充 verified_anchor，开书同步等待由 2.5 秒延长至 6 秒。保留 beta.3 的双语翻译、扩展中心、#117/#118 与精确 chapter_uid + co 同步。
- Improve sync correctness and reduce unnecessary sync overhead.
- 能看到一部分，但**这份 crash 不能严格证明“单击快捷同步失败，而长按→全部重新同步成功”**。原因是当前日志对“单击主页同步”没有单独的事件标记。 能明确看到的是长按路径。比如 beta.7 后段： ```text 20:50:30 ActionSheet fresh key=home_action_functions_sync 20:50:35 item tapped 阅读进度 20:50:39 item tapped 全部重新同步 20:50:43 login renewal completed 20:50:44 remote progress ... 20:50:44 ProgressRecovery freshness checked ... ``` 也就是说，“全部重新同步”之后确实立即进入了完整的认证 → 读取云端 → `ProgressRecovery` 流程。crash 但这里的： ```text ActionSheet fresh key=home_action_functions_sync ``` **不是“单击同步执行了”的证据**，而是同步快捷键的二级 ActionSheet 被构建出来，也就是长按菜单。因此不能拿它来代表单击。 另外一次 16:51:15 也只是记录： ```text ActionSheet fresh key=home_action_functions_sync ``` 之后没有“全部重新同步”，然后你切换了主页栏目。它同样只能证明菜单被打开，不能说明单击同步到底执行了什么。crash 所以目前最准确的结论是： > **你的观察很可能是真的，但当前 crash 的日志粒度不够，不能把这个 A/B 差异直接坐实。** 不过这个问题下一版很好处理。我建议做两件事： ```text 单击主页「同步」 ↓ 和 长按 → 阅读进度 → 全部重新同步 ↓ 强制调用完全同一个 recovery 函数 ``` 同时加明确日志： ```text [SyncAction] source=home_quick action=full_recovery [SyncAction] source=progress_menu_all action=full_recovery ``` 以及结束： ```text [SyncAction] source=home_quick result=success ``` 这样下一份 crash 一眼就能知道两个入口到底有没有走同一条路径。 所以这次我不会说“日志已经证明快捷同步坏了”；**它只明确证明“全部重新同步”确实会启动完整 recovery，而单击快捷同步在当前日志里不可辨认。**这本身就说明下一版需要把两个入口真正硬性统一，而不是继续假设它们等价。
- 修复生包bug
- 统一主页快捷同步与“全部重新同步”的进度恢复流程，并增强设备唤醒后的网络就绪判断。 Description

# v6.0.0 · 2026-10-08

- 正式版基于 6.0.0-beta.1 收口，继承 5.9.1-beta.4 的功能与修复；Schema 保持 136，不把 Beta 发布通道变成正式版通道。
- 保留 5.9 多设备精确阅读进度、云端/本地新旧判断、冲突保护、断线恢复、Progress Recovery Capsule 以及严格的 fail-closed 行为。
- 纳入微信读书书城、搜索与推荐、书架添加/移除、后台书架进度更新、已读完状态双向同步和书架管理授权。
- 主登录与书架管理授权继续使用两套独立凭证；同账号主登录刷新保留书架管理凭证，允许单独撤销书架管理授权。不声称已经完成真正的单凭证统一。
- 保留外文翻译原文/双语/仅译文、书内链接修复、连接复用、扩展中心与 Kindle/Kobo/Android 兼容路径。
- 发布包切换为正式版 6.0.0，默认 OTA 指向 stable-channel/update.json；Beta 发布配置仍只用于内测分支。
