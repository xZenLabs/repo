# v0.5.5 · 2026-11-09

## 月读 v0.5.5

KOReader 插件包：`book.koplugin-v0.5.5.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.4`：

#### 修复

- :bug: (features): 更新后重登改走扩展点，下层不再 require features (eea60c6d)
- :bug: (features): 更新后按磁盘版本重登约定文件，壁纸不必重启才出现 (ae23ca7f)
- :bug: (setting): 去掉我的设备里重复的使用指南 (0a6028e8)

#### 界面

- :lipstick: (library): 封面圆角从逻辑 12px 收到 6px (b404820e)

#### 变更

- :children_crossing: (battery): 用法统计按唤醒/休眠/充电分段显示 (33293716)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.4...v0.5.5

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
