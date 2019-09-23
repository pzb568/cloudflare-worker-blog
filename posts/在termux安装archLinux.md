# termux安装archLinux
## 一、下载
1. git下载

```
pkg install git
cd && git clone https://github.com/sdrausty/TermuxArch
bash TermuxArch/setupTermuxArch.sh
```
2. 如果太慢可以使用wget下载
```
 pkg install wget
 
wget https://sdrausty.github.io/TermuxArch/setupTermuxArch.sh
```
## 二、安装
```
bash setupTermuxArch.sh
```
## 三、启动
```
startarch
```
## 四.修改源及更新
进入arch文件夹
```
cd arch
```
下面安装vim编辑工具
```
pacman -S vim
```
修改源为清华大学
```
vim etc/pacman.d/mirrorlist
```
在这上面添加
```
Server = https://mirrors.tuna.tsinghua.edu.cn/archlinuxarm/aarch64/$repo
```
如下图
![](https://i.bmp.ovh/imgs/2018/12/fee7293b9d02f4bb.jpg)
按esc 键 :wq 保存并退出
## 四、更新系统
```
pacman -Syyu
```
## 五、安装常用软件
```
pacman -S python
pacman -S openssh
pacman -S git
pacman -S vim
```


