# v0.1.9

## 月读 v0.1.9

KOReader 插件包：`book.koplugin-v0.1.9.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.1.8`：

#### 新功能

- :sparkles: (ui): 添加设置项并启用桌面图标打开桌面功能 (2a16975)
- :sparkles: (ai): 优化上下文显示逻辑和实体处理 (c5dcbd8)
- :sparkles: (ai): 优化锁屏组件显示逻辑 (10b2fe4)
- :sparkles: (ai): 优化锁屏组件显示逻辑 (fcd5112)
- :sparkles: (ai): 优化 X-Ray 数据获取逻辑，增加首次初始化和章节增量逻辑 (ebf5ff3)

#### 修复

- :bug: (local): fix book scanning crash and retry logic (176336d)
- :bug: (ui): 修复登录流程中的取消逻辑 (9bc4408)
- :bug: (ui): 修复登录流程中的取消逻辑 (e3766ee)
- :bug: (db): 修复文件移动/重命名逻辑 (9d8ea63)

#### 重构

- :recycle: (auth): 重构 auth 模块逻辑以适配 token 与 wlfstk_smdl 的配对校验 (5b4f2cb)

#### 文档

- :memo: (docs): 更新 xray README.md (2e5dd7f)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.1.8...v0.1.9

# v0.1.8

## 月读 v0.1.8

KOReader 插件包：`book.koplugin-v0.1.8.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.1.7`：

#### 新功能

- :sparkles: (ui): 优化 OPDS 设置界面 (4f995fa)
- :sparkles: (opds): 添加 OPDS 支持 (10b8efb)
- :sparkles: (ai): 更新翻页动画功能门面以绑定 Moon 自身的动画开关 (0dea1b8)
- :sparkles: (ai): 更新翻页动画功能门面以绑定 Moon 自身的动画开关 (aa7edf8)
- :sparkles: (ai): 优化书籍元数据同步逻辑 (c707a32)
- :sparkles: (ai): 优化书籍元数据同步逻辑 (2ffa99a)

#### 修复

- :bug: (http, ui, tests): 修复处理 Content-Length 为 0 的请求和 302 重定向逻辑 (6266e1f)
- :bug: (测试): 修正 system_spec.lua 中的测试逻辑 (c447ea8)
- :bug: (测试): 修正测试脚本中的内存拷贝逻辑 (bfbc311)

#### 重构

- :recycle: (lib): 加载 libz 库并初始化 inflate 函数 (ac74eb1)
- :recycle: (lockscreen): 适配混合模式 source_id 处理 (de59990)

#### 变更

- :fire: (ui): 优化封面下载处理逻辑 (5c3b479)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.1.7...v0.1.8

# v0.1.7

## 月读 v0.1.7

KOReader 插件包：`book.koplugin-v0.1.7.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.1.6`：

#### 修复

- :bug: (api): 修复登录及续期逻辑 (a93f9d6)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.1.6...v0.1.7

# v0.1.6

## 月读 v0.1.6

KOReader 插件包：`book.koplugin-v0.1.6.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.1.5`：

#### 新功能

- :sparkles: (ui): 优化界面样式和布局 (68a8fbd)
- :sparkles: (ui): 优化界面样式和布局 (44a9988)
- :sparkles: (ai): 添加本地 WebDAV 配置支持 (0660a3b)
- :sparkles: (ui): 添加多语言支持并优化票根生成 (4ccd5a3)
- :sparkles: (ui): 添加多语言支持并优化票根生成 (973f787)
- :sparkles: (ui): 添加多语言支持并优化票根生成 (4ec65d2)
- :sparkles: (ui): 添加多语言支持并优化票根生成 (edad981)
- :sparkles: (ui): 添加阅读页侧栏及配置选项 (86ddccc)
- :sparkles: (ai): 添加基于日出时间计算时区的功能 (dadc8cd)
- :sparkles: (ai) 优化封面图片加载逻辑 (a27bce4)
- :sparkles: (ui,feature): 更新多语言文本及同步阅读时间设置 (a071f43)
- :sparkles: (book): 实现书籍封面缓存功能 (d538fd7)
- :sparkles: (ui): 更新语言文件 (a767ae7)
- :sparkles: (ui): 添加书库刷新的假进度弹窗 (5082f0a)
- :sparkles: (db): 支持新旧身份合并及物理路径登记 (0eaad26)
- :sparkles: (ai): add WebDAV 支持 (d97ffb9)
- :sparkles: (ai): 支持处理 azw 文件格式 (98991ae)
- :sparkles: (ai): add AZW3 文档支持 (cbafe61)
- :sparkles: (ai): add AZW3 文档支持 (b647326)
- :sparkles: (ai): 更新 README 内容以反映新功能和改进 (7fff131)

#### 修复

- :bug: (ui,测试): 修复离线时注解同步逻辑 (30e778d)
- :bug: (http): 修复 Basic 认证问题 (4c48302)

#### 界面

- :lipstick: (ui): 添加分享锁屏图功能 (7bb0ffd)

#### 重构

- :recycle: (ui): 优化侧边栏显示逻辑 (5660c79)
- :recycle: (ui): 优化侧边栏翻页条布局 (0c82d0c)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.1.5...v0.1.6

# v0.1.5

## 月读 v0.1.5

KOReader 插件包：`book.koplugin-v0.1.5.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.1.4`：

#### 新功能

- :sparkles: (utils): 更新自动灯光周期配置 (5599759)
- :sparkles: (ai): 新增 WebDAV 连接测试功能 (bb9cce8)
- :sparkles: (ai): 添加翻页动画样式选项并更新测试 (8c79cf8)
- :sparkles: (ai): 添加翻页动画风格设置功能 (0096c30)
- :sparkles: (ai): 添加翻页动画风格设置功能 (b617680)
- :sparkles: (ai): 添加翻页动画风格设置功能 (fe3182c)
- :sparkles: (ai): 添加翻页动画风格设置功能 (f72592a)
- :sparkles: (ai): 添加和更新翻页动画样式 (422cd1b)
- :sparkles: (ai): 添加翻页动画补丁和国际化支持 (7d9d05f)

#### 界面

- :lipstick: (ui): 优化设置界面的按钮行为 (538fd5a)

#### 重构

- :recycle: (ui, tests): 优化首页组件数据刷新逻辑 (7414235)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.1.4...v0.1.5
