# v1.4.7 · 2026-11-15

## 更新说明

- 长按菜单（上传/下载元数据、上传书籍）与选择模式 Plus 菜单改为复用现有批量流程，不再重复实现
- 修复长按菜单上传书籍丢失作者字段、导致标题_作者命名模式失效的问题
- 检查本地 sidecar 前先落盘当前打开书籍的元数据


## What's Changed

- Long-press menu actions (upload/download metadata, upload book) and selection-mode Plus menu actions now reuse the existing batch pipelines instead of duplicating logic
- Fix book upload from the long-press menu dropping the author field, which broke the title_author naming mode
- Flush the currently open book's metadata to disk before checking for its sidecar

# v1.4.5-beta.1 · 2026-09-02

## 更新说明

- 适应bookshelf插件：在bookshelf书架页面执行手势批量操作可自动进入书架的选择模式并获取选中书籍
- 修复云端书籍对话框中的文件夹导航问题：文件夹名称过长时中文截断乱码
- 完善中文翻译

## What's Changed

- Integrate with Bookshelf: batch operations now auto-enter Bookshelf selection mode and retrieve selected books
- Fix garbled text when truncating Chinese folder paths in cloud book dialog navigation
- Improved Chinese translations
