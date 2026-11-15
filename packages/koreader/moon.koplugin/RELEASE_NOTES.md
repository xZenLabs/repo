# v0.5.24 · 2026-11-15

## 月读 v0.5.24

KOReader 插件包：`book.koplugin-v0.5.24.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.23`：

#### 修复

- :bug: (reader): 重排进度只重画弹窗，修复切字体时一直「正在排版」的无限递归 (fccc24bb)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.23...v0.5.24

# v0.5.23 · 2026-11-15

## 月读 v0.5.23

KOReader 插件包：`book.koplugin-v0.5.23.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.22`：

#### 修复

- :bug: (qidian): 书不在书架上时读取进度不再崩溃，七猫同步修复 (37f260b9)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.22...v0.5.23

# v0.5.22 · 2026-11-15

## 月读 v0.5.22

KOReader 插件包：`book.koplugin-v0.5.22.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.21`：

#### 新功能

- :sparkles: (fontmap): 常见字体名自动映射到本机相近字体，书内自带字体单独标注 (6f413793)

#### 修复

- :bug: (bars): 双行底栏容器高度不足时下行进度条向上溢出而非被挤出屏幕 (f28752c6)
- :bug: (rare): 注音回退字体（中文释义）按 DPI 反向缩放，避免字形过大压住正文 (4ca055a2)
- :bug: (fonts): fonts 目录有变化时重扫字体列表，新放入的字体无需重启即可选 (da422551)
- :bug: (fontmap): 自动映射在加载文档时不再读书内字体列表，避免开书崩溃 (4855525b)
- :bug: (share): 书摘卡片分享不再删用户已保存的图，并清理旧临时图 (938ec063)

#### 其他

- :wrench: (iread): 适配新版 API（GET /user/home、只传 id 的参数精简） (7b4557a3)

#### 变更

- :children_crossing: (reader): 开书弹窗显示书名，引擎进度在类上接管以替代原生进度条 (112e9117)
- :children_crossing: (fontmap): 自动弹出与手动打开展示同一份完整字体列表 (83f7c9a2)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.21...v0.5.22

# v0.5.21 · 2026-11-15

## 月读 v0.5.21

KOReader 插件包：`book.koplugin-v0.5.21.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.20`：

#### 新功能

- :sparkles: (reviews): 段评设置页增加画线样式、灰度、透明度、位置选项 (c0f669e5)
- :sparkles: (reviews): 段评画线支持点状、灰度、透明度和上下微调 (af4ea3b4)

#### 变更

- :loud_sound: (lockscreen): 记录锁屏 setup/show 结果，便于排查偶发不弹锁屏图 (a7c897ef)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.20...v0.5.21

# v0.5.20 · 2026-11-15

## 月读 v0.5.20

KOReader 插件包：`book.koplugin-v0.5.20.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.19`：

#### 修复

- :bug: (reader): 切章时保留不可见占位窗，避免窗口栈清空退出 KOReader (f1246bc9)
- :bug: (reader): 切章前校验章节文件并补充读完与切章失败日志 (78560d02)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.19...v0.5.20
