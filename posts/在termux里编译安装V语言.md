---
title: 在termux里编译安装V语言
categories:
  - 软件开发
tags:
  - 编译
  - V语言
keywords:
  - tech
abbrlink: 1feab083
date: 2019-07-11 14:27:45
---
&emsp;&emsp; V语言是一种静态类型的编译型编程语言，它与Go类似，也受到 Oberon、Rust、Swift语言的影响。

V语言是一种非常简单的语言，阅读此文档将花费你大约半小时的时间来学习完几乎整个V语言。

尽管很简单，但它为开发人员提供了很多动力。 任何你可以用其他语言完成的事情，你都可以使用V语言来做。

V语言github地址:https://github.com/vlang/v  
V语言中文社区地址: https://www.v-lang.cn/ 
 
V语言的Linux MACOS安装这里就不演示了，网络上有很多的教程；我这里的教程是在比较小趴的安卓Linux环境程序[termux](https://termux.com)上安装V语言

# 克隆
```
git clone https://github.com/vlang/v
```
# 进入V语言项目文件夹
```
cd v
```
# 编译
```
make
```
# 建立程序软链接
```
ln -s /data/data/com.termux/files/home/v/v /data/data/com.termux/files/usr/bin/v
```
# 查看
```
which v
```
# 启动
```
v
```

![](https://i.bmp.ovh/imgs/2019/07/a0ffa8434fa5c47b.jpg)
#### 




# 

## 

### 

#### 



<!--more-->
