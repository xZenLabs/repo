# v1.0.6

## What's Changed

- Header & Footer: fix crash when tapping an item inside the menu
- Icon picker: optimize search logic and rework showIconPicker to fix crashes on Android
- Icon picker: add label toggle (eye / eye-off) to show or hide icon names in the grid
- Quick Actions editor: add 'New' and 'Action Pool' buttons to action edit dialogs
- Quick Actions editor: refresh panel and bottom bar immediately after add/remove/reorder
- Preset management: add 'Apply preset' to 'Action Pool' ( falls back to defaults if none)
- Bottom bar: fix missing bottom bar after screen rotation on Android
- Bottom bar: fix missing bottom bar when entering History/Collections from another fullscreen view
- Bottom bar: fix crash in History/Collections when handling tabs (add/move/sort/etc.)
- Bottom bar: fix touch zone residue after removing the rightmost tab in History/Collections
- Bottom bar: improve bottom bar show/hide experience in ReaderUI
- Updates: fix occasional crash when checking for updates

# v1.0.5

## What's Changed
- Fix: prevent layout corruption when rotating screen
- Added bottombar to history/collections/favorites

## 更新日志
- 修复旋转屏幕时布局混乱的问题
- 给历史记录/书单/收藏界面添加底部栏

# v1.0.4

## What's Changed
- Fix crash when removing last bottom bar tab (empty tab list handling)
- Fix residual touch handler when removing the rightmost bottom bar tab
- Fix Deselect All not showing when bottom bar tab count reaches max limit
- Move Remove button next to Save in built-in action edit dialog
- Adjust title and author font size in list view
- Fix placeholder cover dim effect not showing when selected in filemanager
- Add 'Hide in PDF' option for bottom bar
- Improve Chinese translations
- 修复底部栏移除最后一个按钮时崩溃闪退的问题（无按钮时显示提示性文字）
- 修复底部栏移除最右边按钮后触摸区域仍为旧按钮的问题
- 修复底部栏因达数量限制而无法批量移除所有按钮的问题
- 将内置动作编辑框的移除按钮放至保存按钮左侧（保持与自定义动作编辑框相同布局）
- 调整显示模式列表视图下标题及作者字体大小（解决字体过大的问题）
- 修复无封面书籍的占位封面及列表视图下的书籍封面无选中效果的问题
- 添加在PDF中隐藏底部栏选项
- 完善中文翻译

# v1.0.3

## What's Changed

- Expose QuickUI bottom bar height globally for SimpleUI compatibility
- Ddisable auto-keyboard popup on action edit dialogs to prevent accidental triggers
- Display release notes when new version is found
- Remove the name field to be compatible with KOReader v2026.07

# v1.0.2

## What's Changed

- feat(bottombar): add overlap toggle for reader view
- fix(qa_settings): hide Remove button when creating new custom action
- fix(main): read plugin version from _meta.lua dynamically
- i18n: add translations for overlap mode
