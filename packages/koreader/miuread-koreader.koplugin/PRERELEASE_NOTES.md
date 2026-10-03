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

# v5.8.0-beta.22 · 2026-09-08

- 正式纳入 jerry-shao 的 PR #73「复用微信读书连接，整本下载耗时下降约四分之一」：下载任务中的目录、阅读页上下文和章节正文分片可复用同一 WeRead TCP/TLS 连接，减少连续请求反复握手带来的等待；请求顺序、节奏与现有限流预算保持不变。
- Keep-Alive 继续严格限定在下载链路，并且只有调用方显式传入 `keepalive=true` 才启用；登录、书架、阅读进度、阅读时长、批注与评论点赞等非下载请求继续使用原有一请求一连接行为。
- 连接复用保持保守边界：仅当响应具有明确长度/分块边界、对端没有要求 `Connection: close`、且当前交换没有异常跳转时才回池；空闲 25 秒自动淘汰，单连接最多复用 64 次，取用前检测陈旧连接。
- 复用连接在空闲期间被服务器关闭时，仅 GET / HEAD 可在确认尚未收到响应字节后透明重建一次；POST 不在连接池层自动重放，继续交给原有上层 retry，避免写请求结果不确定时重复提交。
- 下载正常完成、用户取消或异常退出都会主动关闭连接池；限流冷却和网络恢复探测前也会清理空闲连接。流式图片/大文件继续走原有独立连接，不纳入本次复用。
- 保留 `Config.HTTP_KEEPALIVE=false` 的完整回退开关，并新增 Keep-Alive 专项回归测试与静态验证，覆盖下载链路显式启用、非下载隔离、响应边界、陈旧连接、64 次上限、任务结束清理以及 POST 不透明重放。
- PR 提供的 Kindle Oasis 2 A/B 数据中，同一本 36 章书籍由约 962 秒降至 729 秒，连接数由 272 降至 79；实际收益仍取决于设备、网络和书籍资源结构。
- beta.21 在线评论点赞、beta.20 Issue #105 书架恢复与 100 本无分组提醒、beta.19 阅读时长热路径与 SAFE pending、精确阅读进度、后台下载/熄屏恢复等既有行为全部保持。

# v5.8.0-beta.21 · 2026-09-08

- 合入 mao135308 的 PR #72「为划线评论添加在线点赞」：在阅读评论弹窗中可选显示 `♡ / ♥`，支持在线点赞与取消点赞；功能默认关闭，可在“划线与评论 → 在线评论点赞”单独开启。
- 点赞保持为独立即时 Web 操作，不进入本地批注同步队列，不建立离线待上传任务，也不在请求结果不确定时盲目重放；首次状态未知时先读取微信读书官方状态，避免把已经点过的赞误操作成取消。
- 继续以服务器 `succ` 和 `likesCount` 为准；同一评论请求完成前禁止重复提交，旧弹窗会话的异步返回不会更新新弹窗，登录/账号变化会隔离点赞状态，确认 Web 会话失效后按 `auth_revision` 熔断并提示重新扫码。
- 修复 PR 合并时 `store.lua` 遗留的重复 `preferences` 默认表：只保留 beta.20 的完整设置结构，并在真正生效的 `thoughts` 默认值中加入 `online_likes=false`；Schema 继续保持 135，不引入无意义迁移或启动完整保存。
- 点赞内存缓存由单独的 `is_liked` 扩展为同时保存 `is_liked + likesCount`，关闭后立即重新打开评论弹窗时不会出现爱心已经变成 `♥`、点赞数却暂时回到旧值的状态；两者也共同进入弹窗缓存签名。
- 在线点赞关闭时，评论弹窗打开/关闭恢复 beta.20 原有 `partial` 刷新行为；只有用户主动开启在线点赞时才使用 PR 为交互爱心适配的 `ui` waveform，点赞成功仍优先局部刷新赞区域，避免新功能改变未开启用户的阅读体验。
- 新增在线点赞专项自动回归，验证官方状态读取、点赞/取消点赞 wire 参数、无盲目网络重试、认证恢复边界以及默认关闭；总体验证继续覆盖 beta.20 的 Issue #105 书架恢复、100 本无分组提醒，以及 beta.19 的阅读时长热路径、SAFE pending、精确进度和后台任务稳定性。
