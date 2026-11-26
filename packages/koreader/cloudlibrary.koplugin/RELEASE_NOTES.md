# v1.4.8 · 2026-11-26

## 更新说明
> 本次更新重点在于书籍同步功能不再仅仅适用于书籍，其他任何文件包括图片或设置类文件（比如`settings.reader.lua`也可以上传/下载），只是书籍文件可以自己选择不同云端文件命名模式，其他文件直接以原文件名上传）`  
- 排除目录: 修复元数据自动同步排除目录未持久化保存的问题
- 进度合并: 修复进度合并时 xpointer 跨位数比较错误导致最远进度选择错误的问题
- 书籍同步: 将`is_supported_book`判断后移，允许全部文件上传下载，原书籍上传命名逻辑仅对书籍类有效，非书籍类文件直接按文件名上传
- 元数据同步：过滤非书籍文件并增加相关提示
- 书籍同步：上传/下载对话框文件夹快捷导航行根目录与父目录按钮对调

## What's Changed
> **Key update highlights**: Book‑sync functionality is no longer limited to book files. It supports upload and download for arbitrary file types including images and configuration files (e.g. `settings.reader.lua`). Books offer configurable cloud‑side filename naming schemes; other files are uploaded using their original filenames.
- Excluded_dir: Fix the issue where auto-sync excluded directories were not persisted
- Progress merge: fix incorrect farthest progress selection due to cross-length xpointer comparison
- Book_sync: Postpone`is_supported_book`check, allow all files for upload/download with different upload‑naming branches
- Metadata Sync: filter out non‑book files and add relevant prompts.
- Book Sync: Swap Root Directory and Parent Directory Buttons in Upload/Download Dialog Folder Quick‑Navigation Row

# v1.4.7 · 2026-11-15

## 更新说明
- 长按菜单操作（上传/下载元数据、上传书籍）与选择模式 Plus 菜单操作改为复用现有批量流程，不再重复实现
- 修复长按菜单上传书籍丢失作者字段、导致「标题_作者」命名模式失效的问题
- 检查本地 sidecar 前先落盘当前打开书籍的元数据
> 自动同步增强保护：自动上传完全以本地覆盖云端，故从云端自动合并下载到上传的链条十分重要，一旦断裂就容易在用户不知情的情况下丢失云端数据，故此增强保护
- 下载失败（无网络、未配置、下载出错等）后抑制该书的自动上传，避免用不完整的本地元数据覆盖云端；下载成功或云端无此书（404）后解除抑制，抑制期间手动上传会弹窗确认
- 开启自动上传但未开启自动下载时，提示可选开启自动下载（合并），避免首次上传直接覆盖云端数据
- 开启省心同步模式且有书籍正在阅读时，提示先合并更新当前书，避免用未对齐的本地数据覆盖云端


## What's Changed
- Long-press menu actions (upload/download metadata, upload book) and selection-mode Plus menu actions now reuse the existing batch pipelines instead of duplicating logic
- Fix book upload from the long-press menu dropping the author field, which broke the title_author naming mode
- Flush the currently open book's metadata to disk before checking for its sidecar
> Auto sync protection: auto upload fully overwrites the cloud with local data, so the chain from cloud merge-download to auto upload is critical. If that chain breaks, cloud data can be lost without the user knowing. These protections address that.
- Suppress automatic upload for a book after its download failed (no network, not configured, download errors), to avoid overwriting the cloud with incomplete local metadata; a successful download, or a 404 (book not in cloud) clears the suppression, and manual upload asks for confirmation while suppressed
- When enabling automatic upload while automatic download is off, prompt to optionally enable automatic download (merge), to avoid overwriting cloud data on first upload
- When enabling Worry-Free Sync Mode with a book currently open, prompt to merge-update the current book first, to avoid overwriting the cloud with data that has not been aligned

# v1.4.6 · 2026-09-29

## 更新说明
- 修复坚果云 WebDAV 750 个文件上限导致云端书籍列表获取不完整的问题
- 长按书籍菜单新增「上传元数据(CL) / 下载元数据(CL)/ 上传书籍(CL)」操作
- 选择模式 Plus 菜单新增批量「上传元数据(CL) / 下载元数据(CL) / 上传书籍(CL)」操作

# v1.4.5 · 2026-09-08

## 更新说明
- 适应bookshelf插件：在bookshelf书架页面执行手势批量操作可自动进入书架的选择模式并获取选中书籍
- 修复云端书籍对话框中的文件夹导航问题：文件夹名称过长时中文截断乱码
- 优化非触屏设备下载进度条刷新频率
- 完善中文翻译
## What's Changed
- Integrate with Bookshelf: batch operations now auto-enter Bookshelf selection mode and retrieve selected books
- Fix garbled text when truncating Chinese folder paths in cloud book dialog navigation
- Optimization: Repaint the progress bar once a second on non-touch Kindles to improve download progress feedback
- Improved Chinese translations

# v1.4.4 · 2026-08-16

## 更新说明 

- 云端书籍列表添加目录切换按钮，可快捷切换云端书籍目录
- 优化上传/下载/删除进度对话框，显示书名和进度计数
- 无网络时自动提示开启 WiFi，连接后自动重试
- 优化云端书籍列表刷新逻辑，改善 K3/e-ink 设备体验 #12 #14 
- 为云端书籍列表增加循环翻页导航支持，改善 K3/e-ink 设备体验 #13 
- 检查更新时显示更新说明 #11 
- 完善中文翻译

感谢 @iav  对提升K3设备体验的贡献.

## What's Changed 

- Added quick folder navigation to cloud book dialog for switching cloud directories
- Optimized upload/download/delete progress dialogs with book name and progress counter display
- Add auto WiFi prompt and retry for network-dependent operations
- Optimize cloud book dialog refresh logic for better K3/e-ink experience #12 #14 
- Wrap page navigation for K3/e-ink devices #13 
- Display release notes when new version is found
- Improved Chinese translations #11 

Thanks to @iav  for contributions to improving the K3 device experience.
