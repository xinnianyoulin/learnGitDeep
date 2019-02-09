# electron 使用及打包说明

- v1：将已有项目用 `electron` 整合成桌面应用
- v2：基于 electron 使用 node 模块内容操作系统（electron-vue)

## 调试使用

> 全局安装 `electron`

```cmd
cnpm i electron -g
```

```cmd
electron -v
```

存在版本后说明安装成功

> 运行

在已有项目的 dist 下新建 main.js 及 package.json 文件

在 dist 下 git bash 或者 cmd 下输入命令

```cmd
electron .
```

出现相应应用说明基本环境搭建完成

## 打包成软件

> 全局安装依赖

```cmd
cnpm i electron-builder electron-package core-js -g
```

`%LOCALAPPDATA%` : `C:\Users\Administrator\AppData\Local\electron-builder\cache\` (没有就目录下新建)

将`electron-builder-binaries-winCodeSign-2.4.0.zip`解压至`%LOCALAPPDATA%`

将`electron-v1.8.4-win32-x64.zip`复制到`%LOCALAPPDATA%`

> 文件夹内容例图如下

![](/electron-cache.png)

> build

- 打包成文件夹及绿色免安装（依赖 winCodeSign）

```cmd
electron-builder --dir
```

- 打包成 exe 的安装包（依赖 winCodeSign 和 nsis）

```cmd
electron-builder
```

> 执行成功例图如下

![](/electron-builder.png)

目录下生成 dist 文件夹，内含\*.exe 文件

### 附录

文件下载国内源：`https://npm.taobao.org/mirrors/electron/`

electron-vue：`https://github.com/SimulatedGREG/electron-vue`
