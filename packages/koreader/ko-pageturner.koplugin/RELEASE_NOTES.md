# v0.2.7 · 2026-11-17

## 翻页器 v0.2.7

KOReader 插件包：`pageturner.koplugin-v0.2.7.zip`

安装：解压后将 `pageturner.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

### 更新内容

相对上一版本 `v0.2.6`：

#### 修复

- :bug: (pageturner): 不再把 KPW6 系统透传设备 kindle-input-pt 当翻页器接管（会停掉 input_manager 导致唤醒卡死） (8545b3d)

### 完整对比

https://github.com/AnkioTomas/ko-pageturner/compare/v0.2.6...v0.2.7

# v0.2.6 · 2026-11-17

## 翻页器 v0.2.6

KOReader 插件包：`pageturner.koplugin-v0.2.6.zip`

安装：解压后将 `pageturner.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

### 更新内容

相对上一版本 `v0.2.5`：

#### 新功能

- :sparkles: (pageturner): 确认键可改为锁屏；降低耗电（不息屏默认关、轮询放缓） (0e6e4a9)

#### 修复

- :bug: (pageturner): 休眠前释放输入设备，避免唤醒后 poll ENODEV 卡死原生锁屏 (8b5007b)

### 完整对比

https://github.com/AnkioTomas/ko-pageturner/compare/v0.2.5...v0.2.6

# v0.2.5 · 2026-10-30

## 翻页器 v0.2.5

KOReader 插件包：`pageturner.koplugin-v0.2.5.zip`

安装：解压后将 `pageturner.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

### 更新内容

相对上一版本 `v0.2.4`：

#### 变更

- :children_crossing: (pageturner): 月读设置改挂系统本机三级页 (33c5e73)

### 完整对比

https://github.com/AnkioTomas/ko-pageturner/compare/v0.2.4...v0.2.5

# v0.2.4 · 2026-10-30

## 翻页器 v0.2.4

KOReader 插件包：`pageturner.koplugin-v0.2.4.zip`

安装：解压后将 `pageturner.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

### 更新内容

相对上一版本 `v0.2.3`：

#### 修复

- :bug: (pageturner): Kindle 不息屏改喂 powerd t1，兼顾手动休眠 (64e580b)

### 完整对比

https://github.com/AnkioTomas/ko-pageturner/compare/v0.2.3...v0.2.4

# v0.2.3 · 2026-10-30

## 翻页器 v0.2.3

KOReader 插件包：`pageturner.koplugin-v0.2.3.zip`

安装：解压后将 `pageturner.koplugin` 复制到 KOReader 的 `plugins` 目录，然后重启。

### 更新内容

相对上一版本 `v0.2.2`：

#### 修复

- :bug: (pageturner): 不息屏不再写 preventScreenSaver，恢复手动休眠 (4e26bdc)
- :bug: (pageturner): 不息屏改为会话闩，Click 断连不再误睡 (93ef7a2)

### 完整对比

https://github.com/AnkioTomas/ko-pageturner/compare/v0.2.2...v0.2.3
