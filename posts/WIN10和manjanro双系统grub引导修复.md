---
title: WIN10和manjanro双系统grub引导修复
tags:
  - WIN10
  - Linux
  - manjanro
  - grub
  - 双系统修复
categories:
  - 操作系统
comments: true
abbrlink: 102fd15b
date: 2019-02-26 21:55:54
---

&emsp;&emsp; 安装WIN和Linux双系统时经常出现引导错误而无法加入任何一个系统的情况，这个时间不要重新安装，修复一下grub引导就好，重新安装又需要浪费很多时间及精力，我相信很多人用遇到这种情况，使用写一个教程给大家。

# 修复引导
1. 查看Linux引导硬盘的哪个分区
```
ls
```
2. 会出现
```
(hd0)  (hd0,gpt9)  (hd0,gpt8)...
```
这是硬盘分区信息，分区不一样，显示的有可能会有区别

3. 如果不知道Linux分区信息接下来一个一个测试
```
ls (hd0,gpt9)/
```
如果出现Linux文件结构就说明这是安装Linux的分区，如果不是安照上面命令继续测试，只需要修改括号后最后面的数字
4. 显示Linux文件结构后继续找grub引导文件的位置
```
ls (hd0,gpt8)/grub
```
如果没有x86-64-efi显示引导文件继续下面测试，因为这个是一个没有独立文件夹的引导
```
ls (hd0,gpt8)/boot/grub
```
出现后下面找回引导
5. 设置权限
```
set root=(hd0,gpt8)/boot/grub
```
6. 设置引导
```
set prefix=(hd0,gpt8)/boot/grub
```
7. 修复
```
insmod normal
```
<!--more-->
![](https://i.bmp.ovh/imgs/2019/02/9dc692733b099550.jpg)
8. 进入Linux更新grub找回引导。


