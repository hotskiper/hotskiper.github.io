---
title: 内网切换node版本的简单方法
categories:
- web
tags: 
- nvm
- node版本切换
---

我司大部分项目是使用内网开发，之前要切换node版本的话比较麻烦，需要改环境变量啥的。之前在外网发现了nvm这个好东西，最近在内网试了一下，也是可以用的。

### 首先，外网找一个nvm安装包，要exe的，免安装版的那个还要配环境变量，exe的最简单。外网机安装一下，安装过程中会让你选择是否将计算机中已经安装的node加入到nvm的版本管理中，选择是，重启生效，内网相同操作。

### nvm install node版本号安装对应的node版本，到C:\Users\用户名\AppData\Roaming\nvm目录下，你会发现多了一个对应版本号的文件夹，把这个文件夹拷到内网同一目录下，内网就可以使用对应版本的Node了

### nvm list 查看可用Node版本，nvm use 版本号 切换node版本
