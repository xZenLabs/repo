# v0.4.18 · 2026-11-05

## 月读 v0.4.18

本次更新包含上一正式版本 v0.4.16 之后的全部变更。

### 登录与验证

- 起点、潇湘书院支持直接扫码登录，保留 Cookie 导入；QQ 阅读复用同一套阅文扫码流程。
- 七猫支持本机手机号与短信验证码登录，仅将滑块交互交给远程验证。
- 长佩遇到阅读滑块验证时可通过远程管理完成，不再误报为登录失效。
- 非墨水屏设备的二维码窗口支持在本机打开链接；较长的登录提示支持分页。
- 统一跨平台安全随机源，补充英文和繁体中文翻译。

### 其他更新与修复

- 快捷面板可添加第三方插件入口并自选图标；动作弹窗支持分页和屏幕旋转。
- 阅读进度条可选显示两位总进度百分比；AI 支持手动设置温度；X-Ray 可重置当前书的数据。
- 修复 WebDAV 失败重传及多设备阅读统计隔离、微信图片位置进度同步、番茄登录失效识别、Kavita 系列元数据和卷行显示。
- 修复 LuaSocket 请求体部分发送、旧 Android DNS、PocketBook 解压库、缺失图标字体时闪退及电池健康度显示。
- 保留锁屏 PNG 写出失败原因，修正只拉取书源的同步任务提示。

### 验证

云端完整测试：543 项通过，0 跳过，0 失败；覆盖真实 KOReader 前端与原生渲染、远程管理网页脚本，并检查发布工具的 SQLite 环境隔离。

### 安装

下载 `book.koplugin-v0.4.18.zip`，解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

输入法词库附件：`dictionary.sqlite3`、`dictionary-wubi.sqlite3`、`dictionary-cangjie.sqlite3`、`dictionary-zhuyin.sqlite3`。如需手动安装，下载对应布局的文件，直接放入 KOReader 数据目录的 `.moon/`，与 `book.sqlite3` 同级，无需重命名。

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.16...v0.4.18

# v0.4.16 · 2026-11-04

## 月读 v0.4.16

KOReader 插件包：`book.koplugin-v0.4.16.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.4.15`：

#### 新功能

- :sparkles: (bookorbit): 拉取书架时同步已读状态 (#90) (c5a39848)

#### 修复

- :bug: (remote): 同名 Cookie 有多个时逐个验令牌，不只认第一个 (58394a84)
- :bug: (db): 书库文件损坏时挪开坏库并自动重建 (b4ac6dd5)

#### 界面

- :lipstick: (setting): 设置页提示行统一为 Row.note，词库手动安装改成独立入口 (136a0bfc)

#### 变更

- :loud_sound: (dictionary): 查词回退原生窗时记录是哪个插件按钮导致 (4ddbe6a0)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.15...v0.4.16

# v0.4.15 · 2026-11-04

## 月读 v0.4.15

KOReader 插件包：`book.koplugin-v0.4.15.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.4.14`：

#### 新功能

- :sparkles: (library): 书库「更多」按钮可选关闭、进入详情或弹出菜单 (28b2a17a)

#### 修复

- :bug: (ai): X-Ray 大请求改用 SSE 流式，避免整包等待超时 (7dc7d55d)
- :bug: (local): 开文档时子进程崩溃的书改按文件名入库 (fef59478)

#### 变更

- :loud_sound: (workers): 子进程无结果退出时记录可用内存，便于排查 OOM (7e806585)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.14...v0.4.15

# v0.4.14 · 2026-11-04

## 月读 v0.4.14

KOReader 插件包：`book.koplugin-v0.4.14.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.4.13`：

#### 新功能

- :sparkles: (bars): 顶栏、底栏可设置离屏幕边缘的边距，正文随之让位 (d4fbfbfb)
- :sparkles: (library): 书库封面可设置双击、长按动作，默认无动作 (#86) (7a8eab81)
- :sparkles: (wechat): 时长上报成功后记录书、秒数与小时桶，便于排查阅读时长对不上 (3c0915ff)
- :sparkles: 天气 / 一言等 online 任务不再出现在任务列表和顶栏计数 (f66915d9)
- :sparkles: 一言联网频率可设置：默认 1 小时，可选 10 分钟 / 1 天 / 不联网 (1feb6500)
- :sparkles: (http): 请求支持 IPv6，不通时退回 IPv4 (a987d312)
- :sparkles: (source): 退出登录时清掉这个源的本地记录 (528ec367)
- :sparkles: (reviews): 段评可点进二级回复 (ec0739d3)
- :sparkles: (remote): 清除配置升级为格式化月读数据，入口挪到首页备份面板之后 (86964d87)

#### 修复

- :bug: (translate): 双语对照不再翻译 nav 目录，修复目录无法识别 (125b002f)
- :bug: (http): HTTPS 的 IPv6 异步连接失败时退回 IPv4 (f49efe0b)
- :bug: (lockscreen): 文件夹背景跳过 ._ 隐藏文件，避免解码失败 (6700e717)
- :bug: (panel): 亮度/色温滑块只响应起点在轨道上的拖动 (#87) (4c51c09c)
- :bug: (http): 本机没有 IPv6 路由时不再尝试 AAAA 连接，修复 Kindle 联网后几秒崩溃 (b1aaf0a3)
- :bug: (http): IPv6 失败退回 IPv4 换 socket 前先从 ioloop 摘掉旧 socket (b94df5ed)
- :bug: 当前阅读简介缺失：开书时把文件自带简介补进库 (86ea9f83)
- :bug: (remote): 同一台机器同种浏览器重新授权时替换旧令牌，不再累加 (479c4b09)
- :bug: (subscribe): 订阅换章号时旧排版双语章跟着文章迁移 (1834d792)

#### 性能

- :zap: (copymanga): 页图改为 800 宽 JPEG，长图翻页不再卡 (54942b7f)
- :zap: (reader): 收划线和双语章不再扫工作目录 (65482676)

#### 重构

- :recycle: (battery): 单位按驱动表换算、多电池容量求和，旧电量计不再给假的 100% 健康度 (23c7ccf2)
- :recycle: (audit): 锁屏背景直接 require 外部模块，微信书架落盘改原子写 (529fa842)
- :recycle: (translate): 删掉只转发的 ChapterBi.pathFor (6e1f11bd)
- :recycle: (http): turbo 补丁不再 pcall(require) socket (68313254)
- :recycle: (source): 退出登录按统一任务前缀取消，去掉 kavita 特例和 pcall(require) (5cb568b1)

#### 变更

- :children_crossing: (lockscreen): 生成失败提示只显示错误首行，不再刷整段堆栈 (09343200)
- :children_crossing: (bars): 顶栏、底栏边距微调步长改为 1 (e17fd6fa)
- :children_crossing: (sidebar): 「阅读时长」改名「本机时长」，与累计时长相同时不再重复显示 (a6c3e735)
- :globe_with_meridians: (l10n): 补上退出登录、段评回复和 IPv6 译文 (b94d128d)
- :loud_sound: (reader): 开章关书休眠的耗时按步骤打进 warn (6001cd82)
- :white_check_mark: (source): 退出登录测试桩补上 invalidate (631fde7b)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.13...v0.4.14

# v0.4.13 · 2026-11-02

## 月读 v0.4.13

KOReader 插件包：`book.koplugin-v0.4.13.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.4.12`：

#### 新功能

- :sparkles: feat(wechat): 大书架自动开远程管理并引导到网页导入，导入页带进度 (35ce4016)
- :sparkles: feat(awake): 抽出 utils/awake 防自动休眠，ai/convert/sync 任务执行期间也撑着 (275304c1)
- :sparkles: (remote): 远程管理新增屏幕镜像，可在浏览器点按、长按、滑动操作设备 (29f23e07)
- :sparkles: (reviews): 设置页可调整段评字号 (591d0b5e)
- :sparkles: (legado): 设置页可手动扫描局域网，找回换了 IP 的阅读服务 (468eb81a)
- :sparkles: (wechat): 书架全量回包过大时落盘，交浏览器解码分批导入 (eee437f1)
- :sparkles: (http): 域名可绑定到固定地址，内网不再查 DNS (bf22185c)

#### 修复

- :bug: (wechat): 超限书架待导入时不重复下载，只重弹导入页；同步远端改显式方法表 (4f836748)
- :bug: (storage): 存储页识别 kamare / kindle 插件更新包，使用中不列入可清理 (9be72491)
- :bug: fix(http): 请求超时改为空闲计时，持续收到数据不再超时 (f78cc51f)
- :bug: (desktop): 退出阅读器回桌面时不再因失效的文档缓存报错 (d9708835)
- :bug: (battery): 原装 Paperwhite 3 设计容量按 1408 mAh 算 (08777d23)

#### 界面

- :lipstick: (reviews): 段评气泡改为带左尖角的抗锯齿圆角框，居中且字号随正文缩小 (4b307ef4)

#### 重构

- :recycle: (audit): 删去代理 dns_bind 与版本比较里的多余转换，修正屏幕镜像注释 (e5f0af04)
- :recycle: (kindle): Kindle 书源不依赖 kindle.koplugin 是否已装，插件更新挪进书源设置页 (2bf76059)
- :recycle: (update): 月读、kamare、kindle.koplugin 共用插件更新引擎 (6e0fde3c)
- :recycle: (xray): 改身份与撕墓碑共用同一份表清单 (ff2fceda)

#### 文档

- :memo: (readme): 说明改短，详细步骤改到官网 (ee6b1ba4)

#### 变更

- :white_check_mark: test: 修复四个离线红测试（doccache / device 桩、代理注释误报） (a19f6539)
- :children_crossing: (home): 总阅读卡按量级降精度，几万小时不再被截断 (5fc4ae62)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.12...v0.4.13
