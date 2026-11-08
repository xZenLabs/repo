# v0.5.1 · 2026-11-08

## 月读 v0.5.1

KOReader 插件包：`book.koplugin-v0.5.1.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.0`：

#### 修复

- :bug: (tools): 修复 macOS 模拟器点击被识别为长按 (42e596c3)

#### 界面

- :lipstick: (setting): 账号页为全部内置书源配独立图标 (21c904bc)

#### 变更

- :speech_balloon: (paths): 手动安装路径统一显示 koreader/ 前缀 (051505f7)
- :children_crossing: (guard): 其它插件出错时引导去找对应作者 (5a93268d)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.0...v0.5.1

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
