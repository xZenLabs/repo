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

# v0.5.16 · 2026-11-13

## 月读 v0.5.16

KOReader 插件包：`book.koplugin-v0.5.16.zip`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

输入法整库附件：`dictionary.sqlite3`、`dictionary-wubi.sqlite3`、`dictionary-cangjie.sqlite3`、`dictionary-zhuyin.sqlite3`。手动安装时将对应词库放入 `koreader/.moon/`，与 `book.sqlite3` 同级，无需重命名。

### 更新内容

相对上一实际发布版本 `v0.5.14`：

- **章节摘要恢复（#125）**：先保存裁剪后的请求快照，重启恢复未失败的待办；长按阅读快捷面板「回顾前文」重试失败任务。休眠暂停保留待办，主动取消才撤销。书籍改名、删除与数据清理同步处理待办和在飞请求。提交：`31a83065`。
- **旋转策略（#124）**：短按仍按原方式旋转，有重力传感器时长按选择自动、仅 180° 或关闭自动旋转；复用 KOReader 原生设置，无传感器仍保留手动旋转。提交：`79b0b996`。
- **漫画与内存优化**：fork 后定向释放子进程位图缓存，漫画切片和打包移到子进程，并保护失败时的原件。仅漫画书源下载组装新 CBZ 时处理条漫，已有 CBZ 不检查或重建。提交：`1cfd8707`、`83b7dfd5`、`8f10fdbe`。
- **测试兼容性**：隔离解释测试的配置依赖，修复 Linux CI 的测试桩问题（#125）。提交：`4ca991b1`。

自动恢复要求开启自动章节摘要并配置 AI。旧版已丢失且没有快照的任务需重读章节触发；如果 AI 已处理但结果尚未落盘时退出，恢复可能重复请求并计费。

`v0.5.15` 的发布检查未通过，未创建 Release；该标签保留，不覆盖历史。

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.14...v0.5.16

# v0.5.14 · 2026-11-13

## 月读 v0.5.14

KOReader 插件包：`book.koplugin-v0.5.14.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.13`：

#### 修复

- :bug: (comic): 缺少 tj3SetCroppingRegion 导出时回退到 JPEG 条带解码 (b12be1e5)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.13...v0.5.14

# v0.5.13 · 2026-11-12

## 月读 v0.5.13

KOReader 插件包：`book.koplugin-v0.5.13.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.12`：

#### 新功能

- :sparkles: (update): 支持关闭自动检查更新 (342dfa0e)

#### 修复

- :bug: (share): 书摘导出统一保留彩色 (87bbd235)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.12...v0.5.13

# v0.5.12 · 2026-11-12

## 月读 v0.5.12

KOReader 插件包：`book.koplugin-v0.5.12.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 `koreader/plugins/`，然后重启。

词库 sideload：下载对应布局的词库，直接放入 `koreader/.moon/`
（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.5.11`：

#### 新功能

- :sparkles: (share): 支持把划词和高亮生成书摘图片 (02cc33a8)

#### 修复

- :bug: (webdav): 强制逐目录核对并保护书目 (1c0aeeb8)
- :bug: (core): 修复审计发现的笔记、漫画和书摘问题 (57545c9a)
- :bug: (comic): 打包时按屏宽缩小并切片过高的漫画页 (74cb2aca)
- :bug: (reader): 读完软删除等关书后再提示并设置超时 (f6a317b2)
- :bug: (wechat): 任意路径的脚注 note.png 都回退到自带注标 (d2e7c57b)
- :bug: (local): 换书库目录或搬书时按 md5 保留阅读记录 (6f396fb1)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.5.11...v0.5.12
