# v5.9.1-beta.1 · 2026-10-05

- 修复 beta.19 `passive_exact_cache` 的原生 `chapterUid + wr_data_co` 快照遗漏 `safe=true`：此前同一精确位置可能先记录 `final_position_captured`，Reader 关闭后又被 `upload_progress()` 判成 `position_unavailable`，并留下“有失败记录但没有可执行动作”的 pending；本版统一恢复 `safe / coordinate_safe / precise` 语义，并在启动时一次性修复现有 beta.19 精确 pending。
- 新增 ReadingEnd `Progress Recovery Capsule`：精确 source mapping 失败时，把 Reader 仍存活时捕获的 immutable source anchor、XPointer、显示进度、sequence/epoch 持久化；Home 可直接用保存的锚点重跑本地 source cache / fresh Web Reader source，无需为了新产生的失败记录重新打开书。
- `pending_unresolved_position` 正式进入进度恢复状态机：Home/“全部重新同步”优先执行 saved-anchor recovery，再补全整书坐标、fresh GET 云端、按既有 latest-wins 规则发送或验证；失败详情新增“恢复精确位置”。任何旧记录若缺少安全重放坐标和恢复锚点，会明确作为可清理失效记录，不再出现 `items=1` 但 send/verify/resubmit/coordinate 全为 0 的无解释状态。
- ReadReport 生命周期区分主动停止与真实异常退出：ReadingEnd/进度优先抢占后 worker 正常退出不再记为 `unexpected`，也不会被无意义拉起；Reader 活跃期间真实异常退出仍保留一次自动重启。
- 不改变 beta.19 的多锚点精确映射、beta.18 fresh context、beta.17 progress epoch/conflict lifecycle、beta.15/16 `remote_wire_anchor + fresh GET before POST`、exact cloud readback、remote-first freshness resolver、ProgressFence 与 rollback。网络或 source mapping 暂不可用时继续 fail closed：最多延迟同步，不允许用近似百分比或未知远端状态覆盖云端。Schema 保持 136。

# v5.9.0-beta.14 · 2026-10-03

- 以 beta.12 为代码基线，撤销 beta.13 的跳转前精确 preflight 与主动 idle exact-cache 设计；恢复已经在真机验证有效的“近似落点 → exact verify → text-anchor rescue → 再验证”主链。
- 将远端定位最终失败拆成 hard/soft 两类：落入错误章节继续安全 rollback；已经进入目标章节但章节内 `wr_data_co` 未能精确确认时保留当前章节位置，不再自动跳回，同时继续阻止近似坐标写回云端。
- OpenSync 的 late-remote 保护扩展到实际用户位置操作；云端结果返回前用户已经翻页/跳转时，本轮只保留 `remote_newer_pending`，不再突然抢占阅读位置。
- 阅读结束首先独立保存 KOReader `local_display_progress` 与 XPointer；微信 exact `chapterUid + wr_data_co` 解析失败只进入 `local_coordinate_unresolved`，不再让主页本地进度一起失效。
- 首页/书架引入 `progress_known`：未知进度保持 `nil` 并显示“—”，不再用 `nil → 0%`；RecentHero 优先保留本次 reader-close 的较新本地显示进度。
- exact cache 改为纯被动：只在既有流程已经成功获得原生 `wr_data_co` 时顺手保存，并且仅在退出时 XPointer 完全一致才复用；失败位置仅保存 unresolved snapshot，不启动周期性精确定位。
- 完整保留 beta.12 的 source force-refresh、KOReader subprocess completion、pending/verify recovery、严格 exact co 校验与 fail-closed 云端写入策略。Schema 保持 136。

# v5.9.0-beta.13 · 2026-10-03

- 云端较新位置改为跳转前预验证：候选 XPointer 先在后台反算为 `chapterUid + wr_data_co`，通过 exact / content-gated `verified_near` 后才执行一次可见跳转；预验证失败保持当前页，不再自动“跳过去再 rollback”。
- 本地→微信 source 映射保留长匹配优先；长 anchor `not_found/ambiguous` 后增加边界短 anchor 的唯一匹配 recovery。云端→本地文本搜索也在 56 字符 anchor 失败后按 40/28/18 字符前缀有界降级，仍限定目标章节并由最终 `chapter/co` 预验证兜底；补充 `[ProgressSourceRecovery]` 诊断，严格 exact co 容差不放宽。
- 修复 late-remote 竞态：预验证期间不再屏蔽真实用户翻页；用户已经开始阅读后，即使云端候选随后验证成功，本轮也不会自动抢占当前位置。
- 阅读过程中在页面稳定后异步缓存最近一次可信 `chapter/co + source_xpointer`；退出时即时 resolver 失败且 XPointer 完全一致时复用该缓存，继续走现有 pending/upload/cloud-verify 流程。
- 微信服务器 raw percent 明确作为 protocol metadata；beta.13 新的候选跳转只使用 canonical progress，权威同步仍以 `chapterUid + wr_data_co` 为准。
- 保留 beta.12 的失败 source cache 强制刷新、KOReader 子进程完成确认、单 writer、安全 fence 与云端回读验证；Schema 保持 136。

# v5.9.0-beta.12 · 2026-10-03

- 修复精确位置 recovery 的“假网络刷新”：本地 exact/legacy source cache 已经无法定位 anchor 时，network recovery 会显式绕过旧缓存并重新获取当前章节 `coord_html`，成功后覆盖 exact cache；若新源仍无法定位则继续 fail closed，不上传近似位置。
- 修复 reading-time writer 抢占的 zombie/未 reap 判定：在 `kill(pid, 0)` 之外使用 KOReader `FFIUtil.isSubProcessDone(pid, false)` 确认子进程已经完成，减少已退出 writer 被误判为存活而触发 `time_writer_preempt_timeout`。
- 保留 beta.11 的统一手动 progress recovery、wake online-ready gate、pending/verify 安全语义、rollback/fence、translation 与 Release 流程；不采用 immediate time-writer detach。
- Schema 保持 136。

# v5.9.0-beta.11 · 2026-10-03

- 以 beta.10 为基线，主页短按“同步”、同步状态“全部重新同步”和进度失败页“全部重新同步”统一进入 `_sync_progress_full_recovery()`；入口 `source` 只用于诊断，不再因为 UI 路径不同而改变 progress recovery。
- 所有手动同步在进入共享 progress recovery 前统一执行登录与 Wi-Fi radio gate；保留 `pending_send / submitted_unverified`、verify-first、安全重传和冲突保护，不通过 UI 路径绕过现有安全条件。
- 手动同步即使主页缓存暂时显示 0 个失败项，也会先执行同一 progress verification/recovery pass，再依次处理 SAFE 阅读时间与批注，减少“主页单击无动作、二级菜单可恢复”的路径差异。
- Kindle/设备唤醒后的阅读进度 reconcile 增加 online readiness gate：`NetworkConnected` 不再等同于 API 已可用，优先等待 `online=true`，无显式 online 字段时仅在稳定 `connected` 状态并经过额外 grace 后继续。
- `network_restored` 与 `resume_recheck` 共用 `reader-progress-online` waiter，并增加 `[MiuRead][ResumeSync] waiting_network / network_online / reconcile_started / network_wait_timeout` 诊断日志。
- 暂不采用另一个 beta.9 分支的 time-writer detach/SIGKILL 立即接管方案；`miuread/sync.lua` 保持 beta.10/beta.8 字节不变，继续保留现有 `time_writer_preempt_timeout` 防并发 writer 保护。
- 完整保留 beta.10 的 translation 纯 Lua 顶层、数字 bookId 支持、先测试后建 tag 的 Release workflow 与 CHANGELOG 标题兼容。Schema 仍为 136。
