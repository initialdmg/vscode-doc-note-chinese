# VS Code 更新日志 要点中文翻译

VS Code 正在快速开发迭代，每次更新都能会有很多新增功能和配置变化。个人很喜欢 VS Code 这款编辑器，了解一个编辑器才能真正提高效率，但是常常不记得某个功能 VS Code 到底有没有、怎么用、自己记住以后有没有变化。因此把每个版本（自 1.13）的更新日志中自己需要的功能点翻译下来记录于此。


# [May 2017 (version 1.13)](https://code.visualstudio.com/updates/v1_13)

highlights：

- **默认设置**：默认启用：插件自动更新，编辑区拖拽复制，minimap
- **多光标Ctrl/Cmd + Click**：

## 设置

### 默认设置

- `editor.minimap.enabled` : true   启用minimap
- `workbench.iconTheme`: "vs-seti"  图标主题
- `editor.dragAndDrop`: true    拖拽复制
- `extensions.autoUpdate`：true     插件自动更新
- `window.openFilesInNewWindow`: "off"      在当前 vs code 进程中打开新文件

### 多光标

快捷键 Ctrl+Click

## 编辑器

### 建议列表，文档说明并排显示

当自动完成/建议触发时，按 `Ctrl+Space` 显示详细说明和注释。以后会一直以这种形式显示，除非再次使用 `Ctrl+Space` 关闭。

### 在建议列表中显示 Emmet 缩写

此前使用 Tab 键展开 Emmet，但是常常引起一些问题，与预期操作不同（如有时并不是要展开 Emmet 却展开了）。因此，现在将这一任务放在建议列表中，释放 `Tab` 键，让他做他本该做的事：缩进。

将 `emmet.useNewEmmet` 设置为 `true`，即可启用这一特性。该特性最好与文档建议旁侧显示一起使用，以便在键入的时候预览最终的结果。

![Emmet](https://code.visualstudio.com/images/1_13_emmet.gif)

### Multi cursor snippets

![Multi cursor snippets](https://code.visualstudio.com/images/1_13_snippets-multi-cursor.gif)

### 查找（Find）部件

现在可以调整大小。也不会再遮挡文档的第一行代码。

**新设置**

- 设置`editor.find.autoFindInSelection` 为 `true`，在选择字符或成行的代码时，默认启用在选择中查找。
- 切换在选择中查找 `toggleFindInSelection` 命令快键键：`Alt+L`。
- `editor.find.seedSearchStringFromSelection`: 控制是否将编辑器的选中内容作为搜索词填入到查找组件。


### 折叠控制符

`editor.showFoldingControls`: `mouseover(默认) | always`。控制如何显示编辑器侧边上的折叠控制符。

## 语言支持

### JSX/TSX 组件语法着色

JSX 和 TSX 文件中，表示组件的类的颜色现在将使用其他颜色，以区别普通 HTML 元素。

### 增加可以显示文档建议的 JSDoc 标签

一些JSDoc 标签，如 `@deprecated` 和 `@private` 现在也会显示相关的文档建议了。
