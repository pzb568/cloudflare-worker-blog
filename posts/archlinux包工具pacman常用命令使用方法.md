---
title: archlinux包工具pacman常用命令使用方法
tags:
  - pacman
  - arch
categories:
  - 系统工具
comments: true
mathjax: false
abbrlink: 57793a5c
date: 2019-11-19 23:05:10
---

&emsp;&emsp; Pacman 是一个软件包管理器,，作为ArchLinux发行版的一部分，是 Arch Linux 的一大亮点。它将一个简单的二进制包格式和易用的构建系统结合了起来。不管软件包是来自官方的 Arch 库还是用户自己创建，Pacman 都能方便的管理。
# 查看
## 列出已经安装的软件包
```
pacman -Q
```
## 查看clang包是否已经安装
```
pacman -Q clang
```
## 查看已安装的包python的详细信息
```
pacman -Qi python
```
## 列出已安装包python的所有文件
```
pacman -Ql python
```
## 查找某个文件属于哪个包
```
pacman -Qo /etc/passwd
```
# 查看组
## 查询包组
```
pacman -Sg
```
## 查询包组所包含的软件包
```
pacman -Sg gnome
```
# 搜索
## 搜索virtualbox相关的包
```
pacman -Ss virtualbox
```
## 从数据库中搜索virtualbox的信息
```
pacman -Si virtualbox
```
# 同步升级
## 仅同步源
```
sudo pacman -Sy
```
## 更新系统
```
sudo pacman -Su
```

## 同步源并更新系统
```
sudo pacman -Syu
```
## 同步源后安装包
```
sudo pacman -Sy virtualbox
```
升级时不升级virtualbox包
```
sudo pacman -Su --ignore virtualbox
```
# 安装
## 从本地数据库中获取git的信息，并下载安装
```
sudo pacman -S git
```
## 强制安装virtualbox包
```
sudo pacman -Sf virtualbox
```
## 本地安装
```
cd /var/cache/pacman/pkg
sudo pacman -U virtualbox-5.2.12-1-x86_64.pkg.tar.xz
```
# 删除
## 删除virtualbox
```
sudo pacman -R virtualbox
```
## 强制删除被依赖的包***慎用***
```
sudo pacman -Rd virtualbox
```
## 删除nodejs包及依赖其的包
```
sudo pacman -Rc nodejs
```
## 删除nodejs包及其依赖的包
```
sudo pacman -Rsc nodejs
```
# 清理
## 清理/var/cache/pacman/pkg目录下的旧包
```
sudo pacman -Sc
```
## 清除所有下载的包和数据库
```
sudo pacman -Scc
```

<escape><!-- more --></escape>