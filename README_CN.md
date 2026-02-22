Language: [English](./README.md) | [中文](./README_CN.md)
<br/><br/>

# node-modules

基于 [zyrong/vscode-node-modules](https://github.com/zyrong/vscode-node-modules) fork，增强支持多层级 node_modules 目录结构。

<br/>

## Features

### package.json 悬浮提示

在 `package.json` 文件中将鼠标悬停在 `packageName` 上会出现相关提示。如果此 packageName 对应的 package 已经安装，点击悬浮框中的包名，会跳转到包的安装目录下。

![](https://raw.githubusercontent.com/wangjs-jacky/vscode-node-modules/master/resources/images/hover-pkgjson-pkgname.gif)

### import/require 悬浮提示

在 `.ts` `.js` `.jsx` `.tsx` `.vue` 文件中使用 `import` 或 `require` 导入 `package` 时，鼠标移动到 `PackageName` 上，将会得到相关提示。

![](https://raw.githubusercontent.com/wangjs-jacky/vscode-node-modules/master/resources/images/hover-import-pkgname.gif)

### 跳转到定义

在 package.json 文件中 `按住 ctrl` + `点击 packageName` 将跳转到 node_modules 对应 package 目录下。

![](https://raw.githubusercontent.com/wangjs-jacky/vscode-node-modules/master/resources/images/goToDefine.gif)

### 搜索 Package

对 node_modules 文件夹点击右键，在弹出的菜单中点击搜索 Package，可以对 node_modules 的 package 进行搜索。

![](https://raw.githubusercontent.com/wangjs-jacky/vscode-node-modules/master/resources/images/search-package.gif)

### 搜索 node_modules

在弹出的菜单中，点击搜索 node_modules，可以对 node_modules 进行路径搜索。

![](https://raw.githubusercontent.com/wangjs-jacky/vscode-node-modules/master/resources/images/search-node_modules.gif)

### 复制符号链接实际路径

![](https://raw.githubusercontent.com/wangjs-jacky/vscode-node-modules/master/resources/images/copyRealPath.gif)

<br/>

## 多层级 node_modules 支持

本 fork 版本增强支持了多层级 node_modules 目录结构，适用于以下场景：

### 1. 嵌套 node_modules 查找

当项目存在多层嵌套的 node_modules 结构时（如 `node_modules/package-a/node_modules/package-b`），插件会自动向上遍历查找依赖包，直到找到目标包或到达工作区根目录。

### 2. package-lock.json 支持

支持在 `package-lock.json` 和 `npm-shrinkwrap.json` 中：
- 解析 `packages` 字段下的嵌套包路径
- 解析 `dependencies` 字段下的层级依赖关系
- 自动识别 `.package-lock.json` 文件

### 3. pnpm 目录结构支持

搜索 Package 功能支持 pnpm 的特殊目录结构：
- `node_modules/.pnpm/node_modules/` 目录下的包

### 4. Monorepo 工作区支持

在 monorepo 项目中，支持从子包目录正确解析依赖关系，按照 Node.js 模块解析规则向上查找。

<br/>

## 快捷键

| 功能 | Windows | macOS |
|------|---------|-------|
| 搜索 Package | `Ctrl+K P` | `Cmd+K P` |
| 搜索 node_modules | `Ctrl+K N` | `Cmd+K N` |

<br/>

## 配置项

| 配置项 | 默认值 | 说明 |
|--------|--------|------|
| `node_modules.general.debug` | `false` | 开启调试日志 |
| `node_modules.hovers.pkgName.bundleSize` | `true` | 悬浮提示显示包体积信息 |
| `node_modules.resolve.preserveSymlinks` | `false` | 是否保留符号链接（不解析为真实路径） |

<br/>

## 致谢

本项目 fork 自 [zyrong/vscode-node-modules](https://github.com/zyrong/vscode-node-modules)，感谢原作者的优秀工作。
