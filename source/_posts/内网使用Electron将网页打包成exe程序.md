---
title: 内网使用Electron将网页打包成exe程序
categories:
- web
tags:
- Electron
---
最近有个需求，需要把前端静态页面打包成一个exe程序，百度了一下，主要有[Electron](https://electronjs.org/)和[NW.JS](https://nwjs.org.cn/)这两个构建桌面应用的工具，因为我用的VScode是用Electron构建的，就选它了。

## 步骤

### 1、外网电脑下载一个官方demo，安装完依赖后把整个文件夹传到内网

``` bash
git clone https://github.com/electron/electron-quick-start
cd electron-quick-start
npm install
```

### 2、由于我司内网的node版本比较低，需要切换一下node版本，具体方法可参考另一篇文档

### 3、下载electron-v4.1.1-win32-x64.zip和SHASUMS256.txt-4.1.1到C:\Users\用户名\AppData\Local\electron\Cache下

这两个文件是在外网打包过程中自动下载的，内网下载不了所以构建的时候会报错，从外网电脑对应的目录下拷过来就行

### 4、将页面代码复制到myapp下

需要注意的是如果前端使用了requirejs，后面构建会报错，解决方法是在每个页面所有script之前加入如下js：
``` bash
window.nodeRequire = require;
delete window.require;
delete window.exports;
delete window.module;
```
报错的原因是node里的require和requirejs里的require会冲突

### 5、当前文件夹下执行npm run package

