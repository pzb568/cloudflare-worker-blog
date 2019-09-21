---
title: termux0.66版本修改添加常用按键
tags:
  - termux
  - 常用键
categories:
  - 应用软件
  - 手机软件
  - 安卓系统
comments: true
abbrlink: 25aac357
date: 2019-02-26 20:26:22
---


&emsp;&emsp; termux0.66版本之后又改了快捷键，去掉了左右，home，更新后用的不习惯，并且不方便，可以修改并添加快捷键。
1. 创建.termux文件夹
```
mkdir $HOME/.termux
```
----
2. 在$HOME/.termux/termux.properties 文件中加上下面代码，如果没有安装vim 下面先安装vim

安装vim
```
pkg install vim
```
----
3. 进入文件夹并vim打开termux.properties
```
cd .termux && vim termux.properties
```
<escape><!-- more --></escape>

效果布局1
添加如下内容
```
extra-keys = [['[',']','{','}','&','<','>'],['ESC','/','-','HOME','UP','END',';'],['TAB','CTRL','~','LEFT','DOWN','RIGHT','\"\"']]
```
显示效果如下图
![](https://i.bmp.ovh/imgs/2019/02/147b0f6e881fd8f4.jpg)

效果布局2
```
extra-keys = [['ESC','/','-','HOME','UP','END','PGUP','<','>'],['TAB','CTRL','ALT','LEFT','DOWN','RIGHT','PGDN','[',']'],['$','"','=','{','}','(',')','&','%']]
```
显示效果如下
<img src = 'https://i.bmp.ovh/imgs/2019/04/1ad624dfdd20d41d.jpg' />