# v0.5.4 · 2026-11-09

## 月读 v0.5.4

KOReader 插件包：`book.koplugin-v0.5.4.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.3`：

#### 新功能

- :sparkles: (library): 文件夹用最近阅读封面，并支持封面圆角 (7accc60f)
- :sparkles: (panel): 连续章节快捷面板可手动刷新目录 (7a62589b)

#### 修复

- :bug: (panel): 刷新目录 available 不因会话桩缺方法崩掉 (40a17713)
- :bug: (source): 番茄换号重推书架，取消目录刷新不吃迟到回包 (a77157bd)
- :bug: fix(source): 换账号保留书架和阅读记录 (0f0c0900)
- :bug: (insight): 软删除与下架的已读书仍计入读完 (7b767be7)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.3...v0.5.4

# v0.5.3 · 2026-11-09

## 月读 v0.5.3

KOReader 插件包：`book.koplugin-v0.5.3.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.2`：

#### 修复

- :bug: fix(source): 隔离临时文件并统一 Cookie 更新 (8c65c782)
- :bug: (qidian): 扫码合并书架 Cookie，VIP 不再假报失效 (f24ab548)
- :bug: (copymanga): 登录后落盘密码，401 才能自动重登 (17c5af19)
- :bug: (paths): Android 临时文件改落 .moon/cache/tmp (19c9d7a2)
- :bug: (desktop): 桌面手势 Dispatcher 动作落到 FM 模块 (97130e48)

#### 变更

- :see_no_evil: chore: 停止跟踪本地审计报告 (d1308a53)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.2...v0.5.3

# v0.5.2 · 2026-11-08

## 月读 v0.5.2

KOReader 插件包：`book.koplugin-v0.5.2.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.1`：

#### 修复

- :bug: fix(convert): 统一段首缩进并补齐卷章目录回归 (1cc407f0)
- :bug: fix: 收紧换库、进度决议与书架对账边界 (12fb16f1)
- :bug: fix(wechat): 对齐章节书籍版本与有限重试 (8e793769)
- :bug: fix(emu): 时钟修正仅作用于 macOS 模拟器 (5b0c24d5)
- :bug: fix(main): 保护统一事件入口避免异常崩溃 (0f014b39)
- :bug: fix(l10n): 补齐使用指南译文与设置页测试依赖 (28f5c00b)
- :bug: (jdread): 书架脏 ID 跳过，不再拖死整架同步 (5f87e93d)
- :bug: (store): 换书库目录/服务器时清掉旧书架进度统计 (930dac75)
- :bug: (wechat): 样式表缺失时正文不再丢掉首行缩进 (4a10782d)
- :bug: fix(desktop): 修复统计取消串扰与阅读退出异常 (0cf3ba01)
- :bug: (changpei): 滑块验完后 check<3 沿用已解密正文 (e726a79a)

#### 性能

- :zap: perf(toc): 逐章缓存与异步解析避免目录长卡顿 (cc626414)

#### 文档

- :memo: (release): 更新 KOReader 插件与词库安装路径说明 (bf5e9eba)

#### 变更

- fix(reflow): preserve volume and chapter structure (c31efdad)
- :loud_sound: fix(http): 记录下载响应头解析失败原因 (b52da464)
- :children_crossing: (setting): 设置页与账号页挂上官网使用指南 (4afa9a6f)
- :white_check_mark: (wechat): 补 ZIP TXT 回归，并让 _o 主文件排在续篇前 (9c6000d3)
- fix(wechat): handle TXT chapters in ZIP packages (340e961d)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.1...v0.5.2

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
