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

# v0.5.19 · 2026-11-15

## 月读 v0.5.19

KOReader 插件包：`book.koplugin-v0.5.19.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.18`：

#### 界面

- :lipstick: (reader): 开书与排版进度换成主题进度弹窗 (a0c37efb)

#### 重构

- :recycle: (bars): 删除底栏单栏/双栏开关，行数只看组件的上下行 (3871895b)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.18...v0.5.19

# v0.5.18 · 2026-11-14

## 月读 v0.5.18

KOReader 插件包：`book.koplugin-v0.5.18.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.17`：

#### 新功能

- :sparkles: (legado): 分类取阅读 App 的书架分组，取不到再退回书源标签 (a7d7c511)
- :sparkles: (github): 添加赞助配置 (6700976a)
- :sparkles: (http): 通用 Cookie 罐，请求层自动收发 Set-Cookie (f99e11c5)
- :sparkles: (bars): 支持双行布局并修正组件绘制 (e7ebedff)

#### 修复

- :bug: (bars): 将底栏原生配置局部变量改为 footer_settings (833c972d)
- :bug: (source): 京东/网易/QQ阅读/潇湘/晋江/zlib 改用会话 Cookie 罐 (dc034a9d)
- :bug: (changpei): 复用服务端会话 Cookie，验证后重取正文 (9fa7358f)
- :bug: (reader): 联网与唤醒后补刷章节书目录 (b11a59c0)
- :bug: (desktop): 后台同步连接失败不再弹提示 (614b5a3e)

#### 变更

- :loud_sound: (reader): 增加刷新触发源诊断 (#126) (6bd5d476)
- :loud_sound: (reader): 增加翻页耗时与慢路径日志 (#126) (49d9c0ce)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.17...v0.5.18

# v0.5.17 · 2026-11-13

## 月读 v0.5.17

KOReader 插件包：`book.koplugin-v0.5.17.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.16`：

#### 新功能

- :sparkles: (legado): 接入阅读 App 段评及回复 (0475f7f0)

#### 修复

- :bug: (reader): 漫画分页选择在切章后保持 (c6fc3a74)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.16...v0.5.17
