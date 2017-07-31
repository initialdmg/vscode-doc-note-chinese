# VS Code 更新日志 要点中文翻译

VS Code 正在快速开发迭代，每次更新都能会有很多新增功能和配置变化。个人很喜欢 VS Code 这款编辑器，了解一个编辑器才能真正提高效率，但是常常不记得某个功能 VS Code 到底有没有、怎么用、自己记住以后有没有变化。因此把每个版本（自 1.13）的更新日志中自己需要的功能点翻译下来记录于此。

# [June 2017 (version 1.14)](https://code.visualstudio.com/updates/v1_14)

> 1.14.1: ES5风格类转换为ES6标准类功能由于性能问题禁用了。

highlights：

- 集成终端： 支持查找 - 选择、复制
- 命令面板： 最近最多使用的命令
- 自动缩进： 输入、移动以及复制代码时自动缩进
- 新的 Diff 预览面板：使用 F7 快速切换
- 体验： 64 位版本
- 体验：多目录工作区：在一个窗口打开多个目录


## Workbench

### 轻量更新体验(Lighter update experience)

每次有更新时弹出更新消息让人厌烦。在这个版本中，如果软件有更新，你会在工作台的左下方看到一个指示器（图标）。点击它就可以进行软件更新和其他全局操作（命令板，设置）。

> 在更新推出一段时间后，如果用户依然没有更新，Mac OS 用户会在下次启动时自动更新，Windows 与 Linux 用户会在软件中弹出旧式的消息提醒框。

### 命令面板增强

保留上次输入的命令 - 设置：`workbench.commandPalette.preserveInput`.

最近最多使用 (MRU) 的命令列表 - 最长使用的命令会显示在底部。

显示的条数 - `workbench.commandPalette.history` 设置为`0`禁用此特性。

MRU 启用时，历史记录会默认选择上次的输入，因此无需启用 `workbench.commandPalette.preserveInput`。

新命令：清除历史 - `Clear Commands History`。

### 保存空的工作区(Restore empty workspaces)

空工作区（新建的文件以及已经打开的位于硬盘上的文件，但是并不存在与任何打开的文件夹）现在能够保存输入和 UI 状态。

对应的新配置： `window.restoreWindows`

- `none`：不保存任何 workspace
- `one`： 保存最后一个活动的 workspace（默认）
- `folders`：只保存打开的文件夹
- `all`：保存所有 workspace。

替代的旧配置：`window.reopenFolders` （会在几个版本内完全废弃）

### 关闭没有修改过的文件

快捷键：`Ctrl+K U`。以及 Tab 和 左侧打开的文件视图的右键菜单中。

### 窗口切换

`workbench.action.switchWindow` 切换窗口

`workbench.action.quickSwitchWindow` 快速切换窗口。使用方法：按住修饰键（快捷键中的Ctrl、Alt之类），然后在列表中切换，松开所有按键即可打开选中的文件（夹）。

例如，绑定的快捷键是`Ctrl+R`，使用以下绑定：

```json
{
    "key": "ctrl+r",
    "command": "workbench.action.quickSwitchWindow"
},
{
    "key": "ctrl+r",
    "command": "workbench.action.quickOpenNavigateNext",
    "when": "inWindowsPicker"
}
```

按下 Ctrl+R 调出列表，然后继续按住 Ctrl ，现在按 R 键就可以在列表之间切换，到选中的窗口时松开所有按键即可切换。

## 集成终端

### 重新实现的终端内文本选择功能

新特性：

- 选择和复制多页内容
- **选择全部**命令（右键菜单和命令）
- 双击选择现在可以自动选择 URL 和路径


### 终端内查找

快捷键： `Ctrl + F`。


## Languages

### TypeScript 2.4

VSCode 内嵌 TypeScript 2.4.1。

**自动建议显示父类中的方法**

### 更简单的 TypeScript 构建

[使用任务 Task 编译构建 TypeScript 项目](https://code.visualstudio.com/updates/v1_14#_simpler-building-typescript-using-tasks).

### Markdown 预览中换行的控制

默认的设置是忽略Markdown中的换行。

使用新的 `markdown.preview.breaks`设置，设为 `true`，会将段内的换行处理为 `<br>`。

before：

![不换行](https://code.visualstudio.com/images/1_14_md-no-breaks.png)

after：

![换行](https://code.visualstudio.com/images/1_14_md-breaks.png)

## Editor 编辑器

### Emmet 改进

**多光标支持**

![emmet多光标支持](https://code.visualstudio.com/images/1_14_emmet.gif)


**[Emmet 定制](https://code.visualstudio.com/updates/v1_14#_emmet-abbreviation-improvements)**

### 输入、移动和粘贴时自动缩进

启用: 设置 `editor.autoIndent` 为 `true`。

支持TS, JS, HTML, CSS, JSON 和其他有缩进规则的语言。

### Engineering

**64位支持**

Windows平台现提供64位版本。非 insider 用户最好等待下月的稳定版本。

**在安装64位版本前务必卸载已安装的32位版本**。

### 预览：多根目录工作区

现在在 File 菜单和右键中可以向工作区添加文件夹。搜索支持搜索多个目录。


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
