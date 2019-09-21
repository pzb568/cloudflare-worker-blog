&emsp;&emsp; Linux系统是非常强大的，期中有很多内置命令，随和用户的增加很多人自己贡献了很多优秀的工具，使我们可以更加方便捷的使用及工作。
# exa
>exa是使用 [Rust](https://www.rust-lang.org/zh-CN/)语言编写的**ls**文件列表命令替代品；同时还可以替代**tree**命令。
## 1. 安装
### ubuntu安装
```
sudo apt install exa 
```
### archLinux
```
sudo pacman -S exa
```
### CentOS
```
yum install exa
```
### 安卓termux
```
pkg install exa
```
## 2. 使用
* 查看全部文件
```
exa -a
```
* 查看列表
```
exa -l
```
+ 树形结构查看替代**tree**

```
exa -T
```
[点击这里回到exa](#exa)
# bat 
> `bat` 是一个语法高亮显示和**Git**集成的cat高级版本，也就是说，bat 有 cat的所有功能，且已经集成了代码高亮，和git版本管理的工具，并且会对过长的文件进行自动分页，不会像 cat 一样全部一次打印，所以**bat**完全可以替代cat。
## 安装
### ubuntu
```
sudo apt install bat
```
### archLinux
```
sudo pacman -S bat
```
### 安卓termux
```
pkg install bat
```
## 使用
+ 使用 bat 命令创建一个新的文件:
```
 bat > file.txt
```
- 使用 bat 命令来查看文件内容，只需要:
```
 bat file.txt
```
* 你能同时查看多个文件:
```
bat file1.txt file2.txt
```
+ 将多个文件的内容合并至一个单独文件中:
```
 bat file1.txt file2.txt file3.txt > document.txt
```
- 就像我之前提到的那样，除了浏览和编辑文件以外，bat 命令有一些非常酷的特性。

+ cat 命令以纯文本格式显示文件的内容，而 bat 命令显示了语法高亮和整齐的文本对齐格式
- bat 命令也支持 Git 集成(GIT integration)，这样您就可以轻松查看/编辑 Git 存储库中的文件。 它与 Git 连接可以显示关于索引的修改。

# fd
> **[fd](https://github.com/chinanf-boy/fd-zh)**是一种简单又快速和用户友好的find替代方案。
## 1. 安装
### ubuntu安装
下载最新**.deb**包装从[releases](https://github.com/sharkdp/fd/releases)页面并通过以下方式安装:
```
sudo dpkg -i fd_7.0.0_amd64.deb
```
### archLinux
```
sudo pacman -S fd
```
### Gentoo Linux
```
emerge -av fd
```
### Fedora
```
dnf install fd-find
```
### 安卓termux
```
pkg install fd
```
## 2. 使用

演示

![](doc/df.svg)

[点击这里回到fd](#fd)

<escape><!-- more --></escape>

# ag
> silversearcher-ag—— The silver searcher，这个软件用c编写的，速度极快，用它替代grep。
## 1. 安装
### ubuntu安装
```
sudo apt install silversearcher-ag
```
### archLinux
```
sudo pacman -S silversearcher-ag
```
### 安卓termux
```
pkg install silversearcher-ag
```
## 2. 使用
```
ifconfig | ag inet
```
[点击这里回到ag](#ag)

# axel
>  Axel 是 Linux 下一个不错的HTTP/FTP高速下载工具。支持多线程下载、断点续传，且可以从多个地址或者从一个地址的多个连接来下载同一个文件。适合网速不给力时多线程下载提高下载速度;可以用来替代curl wget 。  

## 1. 下载

### ubuntu
```
sudo apt install axel
```

### CentOS安装

```
yum install axel
```

### MAC 

```
 brew install axel
```

## 2. 使用
* 下载Beyond-光辉岁月
```
axel http://music.163.com/song/media/outer/url?id=346576.mp3
```
+ 指定每移最大下载比特
```
exel -s 1024000 htps://
```
- 设置线程
```
axel -n 10 https://
```
+ 下载到指定位置
```
axel -o /sdcard/ https://
```
[点击这里回到axel](##axel)

# mosh
>Mosh表示移动Shell(Mobile Shell)，是一个用于从客户端跨互联网连接远程服务器的命令行工具。它能用于SSH连接，但是比Secure Shell功能更多。它是一个类似于SSH而带有更多功能的应用。程序最初由Keith Winstein 编写，用于类Unix的操作系统中，发布于GNU GPL V3协议下；Mosh最大的特点是基于UDP方式传输，支持在服务端创建一个临时的Key供客户端一次性连接，退出后失效；也支持通过SSH的配置进行认证，但数据传输本身还是自身的UDP方式，mosh的稳定性是替代ssh最好选择。

## 1. 安装

### ubuntu安装
```
sudo apt install mosh
```
### archLinux
```
sudo pacman -S mosh
```
### MAC
```
brew install mosh
```
## 2. 使用

+ mosh用ssh连接方式
```
mosh --ssh="ssh -p 22" roor@ip
```
[点击这里回到mosh](#mosh)


