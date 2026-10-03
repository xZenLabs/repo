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

# v5.9.0-beta.5 · 2026-10-03

- 重构开书进度对账为非阻塞轻量流程：先立即恢复本机页面，后台只读取一次云端 position metadata；已有精确本地快照时不再先跑完整 source mapping，同一本书 60 秒内仅对“已精确对齐”的缓存结果做读取 debounce。
- 修复 beta.4 的危险 latest-wins 分支：`user_interacted` / 晚到云端不再直接变成 `local wins`。开书冻结 `open_local_snapshot`，优先依据可信 verified anchor 判断哪一端发生变化；双方都变化或无可靠 anchor 时再比较真实阅读事件时间，120 秒 clock-skew grace 内无法安全裁决则进入 conflict。
- 新增持久化 progress write fence：remote fetch 未完成、remote newer、conflict、remote exact unresolved 等状态一律禁止周期、结束阅读和后台 retry 把本机位置写回云端；只有明确 `LOCAL_NEWER`、重新 aligned，或用户显式手动选择本机上传时才解除。
- 本地 freshness 与阅读时长功能解耦：第一页恢复只建立 page baseline，不算新的阅读事件；之后真实翻页/跳转才更新本地阅读事件时间，即使用户关闭阅读时间同步也仍可正确参与 latest-wins。
- `server_raw_percent` 从 canonical position 彻底降级：CloudAnchor、ReadReport 和 finished 判断优先使用 `chapter_uid + co` 映射得到的 canonical progress；服务器异常 `raw_percent=100` 不再把中间章节污染成 100%/finished。
- 收敛 exact-co 定位：优先复用已验证 `chapter_uid + co -> XPointer` 缓存；普通跳转未精确命中后使用微信正文短 text anchor 在对应本地章节恢复 XPointer，再做 exact verify；percent correction 仅保留一次 bounded fallback，避免 964 -> 144 -> 759 一类振荡。
- 阅读时间改为 best-effort：正常尝试一次，运行期空闲后最多再尝试一次；仍失败直接 drop，不再跨重启保存 SAFE time debt，也不再让阅读时间失败污染主页总体同步状态。beta.5 首启会清理 beta.4 遗留的 reading-time retry/failure 状态。
- Schema 继续保持 136；beta.4 的 position-state 标量化与启动 StoreRepair 完整保留。翻译、Extension Center、下载系统、#117/#118 等非同步功能不做行为改动。

# v5.9.0-beta.4 · 2026-10-02

- 修复 5.9 自动续读的崩溃：云端位置对象中的 `sources` 诊断图可能形成自引用，进入 `position_state` 后在下一次 `U.merge()` 触发 LuaJIT stack overflow；现在所有持久化位置状态都压缩为纯标量坐标，并在 merge 前清理旧状态。
- 增加启动自愈：beta.1–beta.3 已写入的循环/膨胀 position snapshot 会在启动时自动压缩，Schema 继续保持 136，不要求用户清空设置或重新登录。
- 修复首次/无共同锚点时的 latest-wins 误判：刚读取到的 `remote_observed` 不再被当成 `verified_anchor`；只有经过精确确认的历史坐标才能作为共同锚点，避免把旧本机位置错误上传覆盖更新的云端位置。
- 开书同步保护的默认本机 fallback 从 2.5 秒延长到 6 秒，更符合“先确认最新位置再开始翻页”的交互；超时文案改为“云端响应较慢，已先使用本机位置；后台继续确认”。
- 保留 beta.3 的 #120 外文翻译、Extension Center UX、#117/#118 增强修复和 `chapter_uid + co` 精确验收，不改变翻译/扩展安装协议。

# v5.9.0-beta.1 · 2026-10-02

- 新增无感 latest-wins 阅读位置解析，取消普通开书的本机/云端选择框。
- 新增开书同步遮罩、2.5 秒本机 fallback、10 秒 late-remote 安全窗口与用户交互保护。
- 新增 8 秒自动定位撤回。
- Schema 136 新增 position_state 双写迁移。
- 微信书架默认云端顺序；读完状态与当前位置分离解析。
- 保持 chapter_uid + co 精确验收，不恢复 percent-equivalent。
