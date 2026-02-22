Language: [English](./README.md) | [中文](./README_CN.md)
<br/><br/>

# node-modules

Forked from [zyrong/vscode-node-modules](https://github.com/zyrong/vscode-node-modules) with enhanced support for multi-level node_modules directory structure.

<br/>

## Features

### Package.json Hover Tip

Hover the mouse over `packageName` in the `package.json` file and a related prompt will appear. If the package corresponding to this packageName is already installed, click the package name in the floating box, and it will jump to the installation directory of the package.

![](https://raw.githubusercontent.com/wangjs-jacky/vscode-node-modules/master/resources/images/hover-pkgjson-pkgname.gif)

### Import/Require Hover Tip

When importing `package` using `import` or `require` in `.ts`, `.js`, `.jsx`, `.tsx`, `.vue` files, move the mouse over the `PackageName`, you will get relevant tips.

![](https://raw.githubusercontent.com/wangjs-jacky/vscode-node-modules/master/resources/images/hover-import-pkgname.gif)

### Go to Definition

In package.json file, `press Ctrl` and `click packageName` to jump to node_modules corresponding package directory.

![](https://raw.githubusercontent.com/wangjs-jacky/vscode-node-modules/master/resources/images/goToDefine.gif)

### Search Package

Right-click the node_modules folder and click Search Package in the pop-up menu to search the node_modules packages.

![](https://raw.githubusercontent.com/wangjs-jacky/vscode-node-modules/master/resources/images/search-package.gif)

### Search node_modules

In the pop-up menu, click Search node_modules to search the node_modules path.

![](https://raw.githubusercontent.com/wangjs-jacky/vscode-node-modules/master/resources/images/search-node_modules.gif)

### Copy Real Path of Symlink

![](https://raw.githubusercontent.com/wangjs-jacky/vscode-node-modules/master/resources/images/copyRealPath.gif)

<br/>

## Multi-level node_modules Support

This fork version enhances support for multi-level node_modules directory structure, suitable for the following scenarios:

### 1. Nested node_modules Lookup

When the project has nested node_modules structure (e.g., `node_modules/package-a/node_modules/package-b`), the extension automatically traverses upward to find dependency packages until the target package is found or the workspace root is reached.

### 2. package-lock.json Support

Support in `package-lock.json` and `npm-shrinkwrap.json`:
- Parse nested package paths under `packages` field
- Parse hierarchical dependency relationships under `dependencies` field
- Automatically recognize `.package-lock.json` files

### 3. pnpm Directory Structure Support

Search Package feature supports pnpm's special directory structure:
- Packages under `node_modules/.pnpm/node_modules/`

### 4. Monorepo Workspace Support

In monorepo projects, supports correctly resolving dependencies from sub-package directories, following Node.js module resolution rules to search upward.

<br/>

## Keyboard Shortcuts

| Feature | Windows | macOS |
|---------|---------|-------|
| Search Package | `Ctrl+K P` | `Cmd+K P` |
| Search node_modules | `Ctrl+K N` | `Cmd+K N` |

<br/>

## Configuration

| Setting | Default | Description |
|---------|---------|-------------|
| `node_modules.general.debug` | `false` | Enable debug logging |
| `node_modules.hovers.pkgName.bundleSize` | `true` | Show bundle size in hover tips |
| `node_modules.resolve.preserveSymlinks` | `false` | Whether to preserve symlinks (not resolve to real paths) |

<br/>

## Acknowledgments

This project is forked from [zyrong/vscode-node-modules](https://github.com/zyrong/vscode-node-modules). Thanks to the original author for the excellent work.
