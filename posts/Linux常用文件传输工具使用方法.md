
&emsp;&emsp; Linux系统之间传送文件，包括Linux服务器和客户端之间，Linux主机和嵌入式Linux平台之间等，以及Linux和windows之间传送文件及同步工具；我们经常在不同的系统中或者主机设备中传输文件或者同步文件，以使用**scp**或者**rsync**及**syncthing**

# ssh登录服务器
## 安装
### ubuntu 
```
sudo apt install ssh
```
### CentOS
```
yum install ssh
```
### MAC
```
brew install ssh
```
### 安卓termux
```
pkg install ssh
```
格式 ssh 端口 服务器$whoami@ip
```
ssh -p 22 user@192.168.1.154
```

# scp
> scp使用的是ssh的传输方式如果安装了ssh就可以直接使用 

## 使用

1. 复制本地文件Caddyfile到远程服务器Home目录  
```
scp -P 8022 Caddyfile u0_a82@192.168.1.105:~/
```
2. 把远程家目录下的Desktop/hello.py拷贝到本地当前目录下的hello.py  
```
scp -P 22 user@ip:Desktop/hello.py hello.py
```
3. 把本地当前目录下的demo拷贝到远程家目录下的Desktop  
```
scp -P port -r demo user@ip:Desktop
```
4. 把远程家目录下的Desktop拷贝到本地当前目录下的demo
```
scp -P port -r user@ip:Desktop demo
```

<escape><!-- more --></escape>

# rsync
1. 本地推送模式： 
格式：rsync -选项 -本地源文件 -远程文件夹 
```
rsync -avz -e "ssh -p 8022" myblog/ u0_a82@192.168.1.104:~/
```
3、远程抓取模式 
格式：rsync -选项 -远程文件夹 -本地目录
```
rsync -avz -P -e "ssh -p 22" user01@192.168.0.108:/tmp/test ./tmp/
```

# syncthing
>**Syncthing**是一个开源免费的文件夹/文件同步神器，支持Android、Linux、Windows、Mac OS X等系统，可以使我们在2台任何系统任何设备之间，实现文件实时同步，很强大。而且数据很安全，不会存储在你的设备以外的其他地方。所有通信都使用TLS进行保护。所使用的加密包括完美的前向保密，以防止窃听者获得对您的数据的访问权限。很适合我们用来搭建私有同步网盘。  

## 安装

### ubuntu
```
sudo apt install syncthing
```
### CentOS
```
yum install syncthing
```
### MAC
```
brew install syncthing
```
### 安卓termux
```
pkg install syncthing
```
## 使用

* 启动
```
syncthing
```
# ftp
## 安装
### ubuntu 
```
sudo apt install ftp
```
### CentOS
```
yum install ftp
```
### MAC 
```
brew install ftp
```
### 安卓termux
```
pkg install ftp
```


### 启动ftp服务
```
tcpsvd -vE 0.0.0.0 1024 ftpd -w /
```
## 使用
```
ftp 192.168.1.3 1024
```
# lftp

## 安装
### ubuntu 
```
sudo apt install lftp
```
### CentOS
```
yum install lftp
```
### MAC 
```
brew install lftp
```
### 安卓termux
```
pkg install lftp
```
## 使用
### 启动lftp服务

### CentOS
```
sudo service vsftpd start
```
### termux
```
tcpsvd -vE 0.0.0.0 8021 lftpd /sdcard
```
## 使用
```
lftp 192.168.1.106 
```


