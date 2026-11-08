# v0.5.0 · 2026-11-08

## 月读 v0.5.0

本次更新包含上一正式版本 v0.4.18 之后的全部变更。

### 书源与书城

- 新接入或大幅补齐：豆瓣、掌阅、塔读、得到、网易云阅读、书旗、快看、知音漫客、知乎盐选、爱看书（18ta）等；多源补齐登录、书架同步、分类与详情元信息。
- 浏览器 Cookie 登录与详情元信息通路打通，网页书源更易保留电脑端登录态。
- 书评 / 段评：豆瓣专栏章评、京东阅读整书书评、快看每话章评、知乎章末段评与表情、番茄段评 emoji、晋江 / 长佩 / QQ 阅读 / 掌阅 / 起点等书城评论与登录加固。
- 潇湘、七猫、爱读、京东阅读等完善游客 / 登录书城、筛选与同步确认；拷贝漫画补齐 API 选线与收藏同步。

### 阅读体验

- 阅读中可从侧栏与快捷面板直达阅读设置，不必先回桌面。
- 书城详情若该书已在架，主按钮改为「开始 / 继续阅读」。
- 电池页增加用法统计：估算每小时耗电与剩余可用时间（保留原有健康度 / 容量读数）。
- Kavita：卷列表续读卡与卷封面，系列页主按钮写明目标卷；续读目标与离线选卷行为统一。

### 稳定性与性能

- 修复本地与 WebDAV 同路径双身份抢进度、进度写到墓碑行的问题；WebDAV 进度同步优先、减少无效传输。
- 修复目录含空标题章节时打开目录崩溃；云端进度冲突未决前不再自动上推；换号 / 登录边界更干净。
- 详情页续读目标一页只算一次；书库「更多」菜单只读选卷入口；Kavita 卷进度改为整列一次查询，不再逐卷扫 resumePage。
- 修复 Legado / reader3 本地 EPUB 章节与图片、稀有字注音筛选与补刷范围、书城分页聚合上限、LuaSec `wantwrite` 误判写失败、缺 inflate 时章节仍可解压等。

### 其他

- 书源译文收口到各自目录；统一书源能力表与限制说明。
- 书库路径含中文或特殊符号时提前提醒换目录。
- CI：KOReader 运行时改为可缓存，并优先经 GitHub API 拉取，避免 Release CDN 504 导致测试跑不到。

### 安装

下载 `book.koplugin-v0.5.0.zip`，解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

输入法词库附件：`dictionary.sqlite3`、`dictionary-wubi.sqlite3`、`dictionary-cangjie.sqlite3`、`dictionary-zhuyin.sqlite3`。如需手动安装，下载对应布局的文件，直接放入 KOReader 数据目录的 `.moon/`，与 `book.sqlite3` 同级，无需重命名。

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.18...v0.5.0

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
