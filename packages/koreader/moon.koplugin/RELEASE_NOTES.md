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

# v0.4.12 · 2026-11-02

## 月读 v0.4.12

KOReader 插件包：`book.koplugin-v0.4.12.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.4.11`：

#### 修复

- :bug: (ui): 数值弹窗太宽时缩小字号，不再截成省略号 (5f7a9c81)

#### 界面

- :lipstick: (insight): 本年页图表和封面墙对齐内容宽 (36056ff1)
- :lipstick: (ui): 主题色一律当深色，主按钮用白字 (d7e32373)

#### 性能

- :zap: (reader): 章节书默认平面渲染，订阅不改模式 (05136332)

#### 重构

- :recycle: (ui): 摊像素余数的算法抽成 utils/spread，三处共用 (71a1c798)
- :recycle: (reader): 渲染模式直接用 identity.ephemeral 判订阅源 (f8c88f2e)

#### 变更

- :coffin: (insight): 去掉阅读目标读取里多余的 or 0，修好设置键扫描 (509278a7)
- :bento: (weather): 天气图标改成彩色透明并补全码表 (2f15d948)
- :children_crossing: (insight): 阅读目标放到统计设置里 (32a0c76d)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.11...v0.4.12

# v0.4.11 · 2026-11-02

## 月读 v0.4.11

KOReader 插件包：`book.koplugin-v0.4.11.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.4.10`：

#### 修复

- :bug: (battery): 按节点真实单位换算，Oasis 健康度不再是 0.1% (c099b4c9)
- :bug: (waveform): kindle_waveform 加上 Kindle Basic 2 (38278cf8)
- :bug: (waveform): kindle_waveform 只对 Kindle Basic 3 生效，删除 MTK 分支 (8b7e82d8)
- :bug: (desktop): 彩色墨水屏换页签闪一次清残影 (3dc69ade)
- :bug: (bluetooth,night): 守护进程掉线自动拉起、夜间刷新走夜间波形 (a27242a4)
- :bug: (remote): 装完插件不再因全局 T 崩溃而跳过重启 (e9a700fc)

#### 变更

- :rewind: (desktop): 换页签改回 ui，彩色屏不再闪 (c7afbae7)
- :rewind: (night): 撤回夜间波形改动，kindle_waveform 保持原范围 (d5080d94)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.10...v0.4.11

# v0.4.10 · 2026-11-01

## 月读 v0.4.10

KOReader 插件包：`book.koplugin-v0.4.10.zip`

输入法词库（整库，手动 sideload）：`dictionary.sqlite3 dictionary-wubi.sqlite3 dictionary-cangjie.sqlite3 dictionary-zhuyin.sqlite3`

安装：解压后将 `book.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

词库 sideload：下载对应布局的词库，直接放入 KOReader 数据目录下的
`.moon/`（与 `book.sqlite3` 同级）。附件已使用最终文件名，无需重命名。

### 更新内容

相对上一版本 `v0.4.9`：

#### 修复

- :bug: (dictionary): 单独开词典不再弹出 KOReader 词典窗 (442a2b42)

#### 重构

- :recycle: (l10n): 删除已不用的「冷暖色调」词条 (dca3874a)

#### 变更

- :children_crossing: (panel): 灯光滑块按硬件档拖动和逐档调节 (08122a10)

### 完整对比

https://github.com/AnkioTomas/moon/compare/v0.4.9...v0.4.10

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
