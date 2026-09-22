# v1.1.0-beta.2

## 更新说明
- 侧边栏: 增加侧边栏快捷菜单（竖滑翻页、横滑拖动，长按按钮-编辑，长按上翻页-设置，长按下翻页-动作池，无按钮数量限制)
- 快捷操作: 优化（阅读器、UI字体切换、页眉页脚）字体列表-字体预览、最近排序、选中最前
- 快捷操作: 添加阅读滑块（字号、间距、样式微调等）的内置动作/手势操作-长按滑块弹出滑块列表（勾选以添加至顶部面板）、长按右侧数值重置为默认、长按左边标签弹出阅读滑块或重置为默认
- 快捷操作: 添加更多流行插件的内置动作（到动作池中添加至顶部面板/底部栏/侧边栏）
- 快捷操作: 给依赖插件的内置动作做前置检查-不可用会在动作池列表显示为灰，全选添加会自动过滤排除，顶部面板/底部栏/侧边栏按钮自动过滤排除
- 快捷操作: 在顶部面板/底部栏/侧边栏彻底删除某动作时联动删除其他栏上的相同动作按钮（避免空引用）
- 顶部面板: 修复点击顶部弹出菜单时误触前光滑块、重构滑块菜单（长按滑块以添加更多阅读滑块至顶部面板）
- 顶部面板: 添加分页行（默认3行1页，行上按钮可快速切换按钮形状、显/隐标签、一页几行，可隐藏、可滑动翻页），移除最大66个的数量限制
- 书库封面: 给进度为0%和100%的书籍也添加进度徽章
- 书库封面: 支持识别simpleui虚拟文件夹（作者/系列/标签）路径中的书籍图片从而正确绘制虚拟文件夹封面（封面网格&图片列表均适用）
- 页眉页脚: 阅读界面显示底部栏时自动隐藏页脚
- 底部栏：搜素结果界面也显示底部栏
- 底部栏：添加阅读器界面显示/隐藏底部栏的手势操作
- 其他: 完善中文翻译

# v1.1.0-beta.1

## What's Changed

- Vertical Bar: add vertical bar as quick menu (swipe to page or move,long-press to edit/add buttons, open the settings menu)
- Quick Actions: improve the font list both in Font List、UI Font Switcher&HF font (font preview + recently-selected sorting)
- Quick Actions: add reader sliders as built-in action and dispatcher action(long-press to bring up a settings dialog, check the box to add it to the panel)
- Quick Actions: add more built-in actions for popular koplugins(find them in actio pools)
- Quick Actions: cascade-delete custom action from all bars to avoid orphaned ids
- Panel: fix accidental touch issue in slider and refactor the slider menu(long-press slider to add more)
- Panel: add pagination (default 3 rows per page-can be changed by tab +/-) with chevron pager and swipe to flip pages; remove the 66-button cap
- Cover: show status icons on the progress badge at 0% and 100%
- Cover: support SimpleUI virtual paths for folder covers (Mosaic & List)
- Header & Footer: hide footer while the QuickUI bottom bar is shown in the reader
- Bottom bar: inject into FileManager via FileManager.setupLayout (one-shot injection)
- Bottom bar: show on filesearch results screen
- Bottom bar: add dispatcher action-toggle bottom bar in reader
- i18n: improve Chinese translation

# v1.0.7-beta.9

## What's Changed

- Vertical Bar: Add vertical bar as quick menu (swipe to page or move,long-press to edit/add buttons, open the settings menu)
- Quick Actions: improve the font list in both Font List and UI Font Switcher (font preview + recently-selected sorting)
- Quick Actions: add reader sliders as built-in action and dispatcher action(long-press to bring up a settings dialog, check the box to add it to the panel)
- Quick Actions: add more built-in actions for popular koplugins(find them in actio pools)
- Quick Actions: cascade-delete custom action from all bars to avoid orphaned ids
- Panel: fix accidental touch issue in slider and refactor the slider menu
- Panel: add pagination (default 3 rows per page-can be changed by tab +/-) with chevron pager and swipe to flip pages; remove the 66-button cap
- Cover: show status icons on the progress badge at 0% and 100%
- Cover: support SimpleUI virtual paths for folder covers (Mosaic & List)
- Header & Footer: hide footer while the QuickUI bottom bar is shown in the reader
- Bottom bar: inject into FileManager via FileManager.setupLayout (one-shot injection)
- Bottom bar: show on filesearch results screen
- Bottom bar: add dispatcher action-toggle bottom bar in reader
- i18n: improve Chinese translation

# v1.0.7-beta.8

## What's Changed

- Vertical Bar: Add vertical bar as quick menu (swipe to page or move,long-press to edit/add buttons, open the settings menu)
- Quick Actions: improve the font list in both Font List and UI Font Switcher (font preview + recently-selected sorting)
- Quick Actions: add reader sliders as built-in action and dispatcher action(long-press to bring up a settings dialog, check the box to add it to the panel)
- Quick Actions: add more built-in actions for popular koplugins(find them in actio pools)
- Panel: fix accidental touch issue in slider and refactor the slider menu
- Panel: add pagination (default 3 rows per page-can be changed by tab +/-) with chevron pager and swipe to flip pages; remove the 66-button cap
- Cover: show status icons on the progress badge at 0% and 100%
- Cover: support SimpleUI virtual paths for folder covers (Mosaic & List)
- Header & Footer: hide footer while the QuickUI bottom bar is shown in the reader
- Bottom bar: inject into FileManager via FileManager.setupLayout (one-shot injection)
- Bottom bar: show on filesearch results screen
- Bottom bar: add dispatcher action-toggle bottom bar in reader
- i18n: improve Chinese translation

# v1.0.7-beta.7

## What's Changed

- Vertical Bar: Add vertical bar as quick menu (swipe to page or move,long-press to edit buttons / open the settings menu)
- Quick Actions: improve the font list in both Font List and UI Font Switcher (font preview + recently-selected sorting)
- Quick Actions: add reader sliders as built-in action, long-press to bring up a settings dialog, check the box to add it to the panel
- Quick Actions: add more built-in actions for popular koplugins
- Panel: fix accidental touch issue in slider and refactor the slider menu
- Panel: add pagination (3 rows per page) with chevron pager and swipe to flip pages; remove the 66-button cap
- Cover: show status icons on the progress badge at 0% and 100%
- Cover: support SimpleUI virtual paths for folder covers (Mosaic & List)
- Header & Footer: hide footer while the QuickUI bottom bar is shown in the reader
- Bottom bar: inject into FileManager via FileManager.setupLayout (one-shot injection)
- Bottom bar: show on filesearch results screen
- Bottom bar: add Dispatcher action: toggle bottom bar in reader
- i18n: improve Chinese translation
