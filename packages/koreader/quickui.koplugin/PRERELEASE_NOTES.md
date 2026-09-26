# v1.2.0-beta.1

## 更新说明
> 新增书籍元数据编辑模块（标题、作者、系列、分类、语言、出版社、简介）
> 💡 **Inspiration**:
> [zenos.koplugin](https://github.com/xZenLabs/zen-os)
>  [metadata.koplugin](https://github.com/ZHA30/metadata.koplugin) 
- 元数据：支持 EPUB 内嵌元数据读写，可恢复
- 元数据：非 EPUB 书籍的元数据保存到sdr文件
- 元数据：长按书籍即可打开「编辑元数据」，支持文件管理器、历史记录、收藏集、文件搜索
- 元数据：在线元数据源 —— 豆瓣、Google Books、Hardcover、Open Library
- 元数据：搜索源选择界面支持配置各自的 API key、修改搜索关键词、分页预览结果
- 元数据：逐字段应用结果，手动修改过的字段不会被覆盖
- 元数据：恢复上一版元数据（仅 EPUB，单步撤销）
- 元数据：Dispatcher 动作 QuickUI_EditMetadata，可绑手势或快捷键
- 元数据：QuickUI 设置新增「元数据设置」子菜单，含「启用元数据编辑器」开关
- 元数据：支持标准预设系统（保存 / 应用 / 重置）
