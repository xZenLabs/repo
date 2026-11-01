# v0.4.9 · 2026-11-01

## 月读 v0.4.9

KOReader 插件包：`book.koplugin-v0.4.9.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.4.8`：

#### 新功能

- :sparkles: (lockscreen): 第三方可以登记锁屏背景 (5c616a78)
- :sparkles: (lockscreen): 第三方可以登记锁屏主体 (64a6eaa1)
- :sparkles: (lookup): 查词面板可以改正选中的词 (378b6092)
- :sparkles: (remote): 更新页可以安装其它插件 (ec1eca4d)
- :sparkles: (reviews): 阅读快捷面板可以开关段评 (ca0675e4)
- :sparkles: (battery): 设置页看健康度、循环次数和充放电 (4bba3b57)
- :sparkles: (reader): 读完已缓存的书可以清理缓存 (d3278765)

#### 修复

- :bug: (reader): 页内标记层的公共绘制步骤也经 guard，出错不再反复重绘崩溃 (a0ddf9bd)
- :bug: (sidebar): 票根图只留当前这张，分享链接带文件修改时间与大小 (f499c808)
- :bug: (translate): 双语对照遇到损坏的待译行时按失败结束，不再当成已翻译 (d58c44f9)
- :bug: (storage): 清理结果按文件是否真的删掉来报，删掉空的设置入口 (fa0f5291)
- :bug: (detail): 有简介时不再挤掉路径 (7d1ae735)
- :bug: (download): 下载中不休眠，断流就换源 (0d237e29)
- :bug: (reader): 整本书页码跟章内用同一套序号 (fa8ebcb9)
- :bug: (reader): 下划线按墨迹居中，不再贴行框底 (6bac3716)
- :bug: (animation): 开翻页动画时 Kindle 字体不再发灰 (9e5f01e2)
- :bug: (animation): 备份丢失时仍能关掉翻页动画 (b0ca8aab)
- :bug: (translate): 整书待译原文不再撑爆 worker 帧 (ed4e6f91)
- :bug: (progress): 换章后不再拿旧进度弹冲突 (d49e7276)
- :bug: (reader): 侧栏书签和书摘按类型分开 (d9a5986a)
- :bug: (shelf): 没进组清掉旧分类，番茄按手机时间排 (240e8ce6)
- :bug: (reader): 章内页码不再和全书页码显示成同一个数 (10538804)
- :bug: (local): 切换本地书设置不再回到设置根页 (0bc1e489)
- :bug: (jjwxc): 晋江收藏翻完再对账，已购章能解开 (177dbc91)
- :bug: (panel): 亮度滑块最低为 1，拖到底不再关灯 (4ed5a26e)
- :bug: (reader): 开书用已同步进度覆盖旧边车 (77dd01a0)
- :bug: (home): 单页底部不再留翻页条，挤不下时只压封面列表 (07b303a6)
- :bug: (bluetooth): 关蓝牙前放开 uhid，避免界面卡死 (a38a0505)
- :bug: (reflow): 书已关闭时取字不再抛错 (0e5b07cc)
- :bug: (reader): 关书后刷新书架不再空引用崩溃 (4b38b2e7)
- :bug: (sidebar): 换书分享的票根不再是第一本 (6905d64b)
- :bug: (desktop): 软删除的书在详情里能恢复 (5d043ade)

#### 界面

- :lipstick: (input): 输入框不再套胶囊圆角 (1b6c6e67)
- :lipstick: (reader): 划词拖动手柄按字符落点 (a55ee669)
- :lipstick: (reviews): 段评页直接开关各账号的显示段评 (389e46bc)
- :lipstick: (setting): 统计导入与清除挪到统计页 (aae2bf5e)
- :lipstick: (home): 最近阅读卡片的书名作者进度可以分别关掉 (e301c9d0)
- :lipstick: (setting): 我的设备补上名称头像和三行读数 (79b993b6)
- :lipstick: (storage): 月读占用按类说明，可清理的按条删 (06bf428a)
- :lipstick: (setting): 存储和运行状态挪进我的设备 (c3cf6cbd)
- :lipstick: (setting): 设置根页改成设备与我的设备 (6c780e38)

#### 重构

- :recycle: (ui): 删除无意义的 pcall 与类型转换，波形钩子经 Guard 调用 (98135f69)
- :recycle: (utils): 文件读取与目录列表收口到 utils/fs，反馈群地址只留一份 (5de39836)

#### 变更

- :white_check_mark: (reader): 阅读页测试补上 getSource 桩 (6d680a10)
- :speech_balloon: (manage): 已停用的功能不再写成重启后停用 (e1ddb019)
- :speech_balloon: (fanqie): 登录提示改成怎么扫码 (3575ec31)
- :speech_balloon: (source): 登录失效提示写成逐步操作 (313b85b6)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.8...v0.4.9

# v0.4.8 · 2026-10-31

## 月读 v0.4.8

KOReader 插件包：`book.koplugin-v0.4.8.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.4.7`：

#### 新功能

- :sparkles: (rare): 行间标注颜色可在灰色与黑色间切换 (bd108fca)
- :sparkles: (source): 书架分类可选自定义分组，不再与题材混用 (d322122a)
- :sparkles: (subscribe): 网页在线源增加精选全文与合集 (389e644c)

#### 修复

- :bug: (reader): 恢复位置抛错也清标志；补齐 LuaLS 与 l10n 缺项 (007e1f5b)
- :bug: (home): 最近阅读卡片圆角不再露白，立体侧封面补回阴影 (0e935e9f)
- :bug: (source): ext.kavita / ext.bookorbit 并入内置源时一次性迁移旧数据 (a58bb316)
- :bug: (desktop): 后台同步只把本机不可达当离线，补齐过期的分类用例 (62e2bbb2)
- :bug: (ui): raised 卡片右下角不再露出白色矩形 (b4c1c46d)
- :bug: (desktop): 唤醒半联网时后台同步不再弹 Could not connect (3057e4a1)
- :bug: (ui): Box 圆角裁切对 cdata 像素也做 RGB32 快照 (48df8978)

#### 变更

- :label: (lint): 清掉最后 7 条 LuaLS 警告 (e4a5ec5b)
- :white_check_mark: (source): 补分类开关的离线用例 (283911a1)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.7...v0.4.8

# v0.4.7 · 2026-10-30

## 月读 v0.4.7

KOReader 插件包：`book.koplugin-v0.4.7.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.4.6`：

#### 新功能

- :sparkles: (lockscreen): 海报可按最近阅读/添加排序，未齐资源跟锁屏次数重出 (aa6dbb5b)
- :sparkles: (rare): WordWise 释义与注音分流，修空格断词 (f10780f3)
- :sparkles: (meta): 每个源和 feature 增加 _meta.lua，启用页据此展示 (fa1f2bc0)
- :sparkles: (home): 首页组件支持上下左右外边距 (30043e7a)
- :sparkles: (home): 最近阅读卡片增加立体透视布局 (357ffc58)
- :sparkles: (themes): 主题色增加墨黑，彩屏可开彩色又保持字迹清楚 (7b44dc0e)
- :sparkles: (kindle): Kindle 书库的书支持编辑元信息 (f14f04a2)

#### 修复

- :bug: (ci): 修圆角截角色值崩溃，清 WordWise 废键与边界误伤 (82d14af3)
- :bug: (lockscreen): 熄屏别盖底栏，唤醒后刷新锁屏图 (4ba6e489)
- :bug: (wechat): 进度推不上时丢掉脏行，别拖死整源同步 (240f6db4)
- :bug: (reader): 开书恢复进度不再误触发翻页动画 (2996cc14)
- :bug: (themes): 柔和主题封面四角都圆，别再只有顶边圆底边方 (04dafe76)
- :bug: (reader): 扫盘根目录之外的 local 行不再当书架成员，修第三方插件章节弹结束页 (ab4d549d)

#### 性能

- :zap: (lockscreen): 立体封面复用梯形缓存，合成与未齐重试别堵主线程 (676c5863)

#### 重构

- :recycle: (source): kavita / bookorbit 并入内置源，去掉 ext 目录 (16e0bd3f)

#### 变更

- :children_crossing: (xray): 识别档位改为居中单选弹窗 (00cd46a1)
- :children_crossing: (setting): 根页增加游戏分组，空组不显示 (e975c970)
- :children_crossing: (setting): 桌面组分栏，页面收图书馆订阅书城统计 (26d1aac0)
- :children_crossing: (setting): 根页改成分组目录，阅读组再拆三类 (0a1bb33c)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.6...v0.4.7

# v0.4.6 · 2026-10-30

## 月读 v0.4.6

KOReader 插件包：`book.koplugin-v0.4.6.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

拓展书源（可选，需同时安装月读）：`moonsource-kavita.koplugin-v0.4.6.zip`（Kavita）、
`moonsource-bookorbit.koplugin-v0.4.6.zip`（BookOrbit）。解压后同样放进 `plugins` 目录。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.4.5`：

#### 新功能

- :sparkles: (home): 最近阅读可隐藏已读完 (02643d53)

#### 修复

- :bug: (reader): 库外文件不再登记接管，不弹「本书已读完」 (623e5952)
- :bug: (bluetooth): 关 Wi-Fi 带崩后按 wanted 自动拉起 (480b5450)
- :bug: (passcode): 横屏解锁临时竖屏，避免底行被裁 (26242322)

#### 变更

- :globe_with_meridians: (l10n): 补「✓ 隐藏已读完」英文与繁体翻译，修 CI (e3206237)
- :white_check_mark: (home): 覆盖最近阅读隐藏已读完 (21bc23dd)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.5...v0.4.6

# v0.4.5 · 2026-10-29

## 月读 v0.4.5

KOReader 插件包：`book.koplugin-v0.4.5.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

拓展书源（可选，需同时安装月读）：`moonsource-kavita.koplugin-v0.4.5.zip`（Kavita）、
`moonsource-bookorbit.koplugin-v0.4.5.zip`（BookOrbit）。解压后同样放进 `plugins` 目录。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.4.4`：

#### 修复

- :bug: (remote): 日志脱敏注释去掉源名，通过 feature 边界检查 (8585375f)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.4...v0.4.5
