
&emsp;&emsp; Aria2 是一个用于 Linux、Windows 和 Mac OSX 的轻量级、多协议和多源的命令行下载管理器/实用程序。它支持 HTTP/HTTPS、FTP、SFTP、BitTorrent 和 Metalink。aria2 可以通过内置的 JSON-RPC 和 XML-RPC 接口操作。它支持多线程，可以使用多个源或协议下载文件，确实可以加速并尽可能多的完成下载。它非常轻量级，不需要太多的内存和 CPU。我们可以使用它作为 BitTorrent 客户端，因为它有所有你想要的 BitTorrent 客户端的功能。
&emsp;&emsp; 我们可以很容易的在所有的 Linux 发行版上安装 aria2 命令行下载器，例如 Debian、 Ubuntu、 Mint、 RHEL、 CentOS、 Fedora、 suse、 openSUSE、 Arch Linux、 Manjaro、 Mageia 等等……只需要输入下面的命令安装即可。对于 CentOS、 RHEL 系统，我们需要开启 uget 或者 RPMForge 库的支持。


# aria2 安装
1. Debian、 Ubuntu 和 Mint
```
sudo apt install aria2
```
2. CentOS、 RHEL、 Fedora 21 和更早些的操作系统]
```
yum install aria2
```
3. Fedora 22 和 之后的系统
```
dnf install aria2
```
4. suse 和 openSUSE
```
zypper install wget
```
5. Mageia
```
urpmi aria2
```
6. Arch Linux
```
sudo pacman -S aria2
```
7. 安卓系统termux
```
pkg install aria2
```
# 图形化aria2下载
## 一、使用Termux在本地搭建Aria2+AriaNg
1. 下载需要的Packages
```
pkg in wget unzip aria2 tmux
```
2. 下载Caddy
这样因为Caddy配置起来比较容易,所以用Caddy当HTTP Server.
```
cd~
wget -qO- https://getcaddy.com | bash -s personal
```
3. 下载AriaNg并解压
```
wget https://github.com/mayswind/AriaNg-DailyBuild/archive/master.zip
unzip master.zip
mv AriaNg-DailyBuild-master AriaNg
rm master.zip
```
4. 配置Caddy
```
cd~
vim Caddyfile 
```
在vim输入（:i编辑,:wq退出并保存）
```
:8080 {
root /data/data/com.termux/files/home/AriaNg
gzip
}
```
5. 启动
输入tmux
在新建的窗口中输入 启动Aria2
```
aria2c --enable-rpc --rpc-listen-all=true --rpc-allow-origin-all -c
```
按Ctrl+b之后再按d返回之前的窗口，将此窗口放在后台执行（输入tmux attach能够重新进入,按Ctrl+b之后再按&关闭当前tmux窗口）
返回后启动AriaNg,输入
```
cd~
caddy
```
6.访问
打开浏览器地址栏输入
127.0.0.1:8080
<escape><!-- more --></escape>
![](01.jpg)
7. 下载BT种文文件需要设置BT服务器
https://github.com/ngosang/trackerslist/blob/master/README.md
在ariaNg设置中找到BT设置BT服务器填入以链接中的内容并附上BT服务器
https://raw.githubusercontent.com/ngosang/trackerslist/master/trackers_best_ip.txt
```
udp://62.138.0.158:6969/announce

udp://188.241.58.209:6969/announce

udp://62.210.79.110:1337/announce

udp://185.225.17.100:1337/announce

udp://151.80.120.112:2710/announce

udp://208.83.20.20:6969/announce

udp://184.105.151.164:6969/announce

udp://176.113.68.67:8080/announce

udp://51.15.40.114:80/announce

http://176.113.71.19:6961/announce

udp://176.113.68.66:6961/announce

udp://91.216.110.52:451/announce

udp://5.206.28.90:6969/announce

udp://188.246.227.212:80/announce

udp://5.2.79.219:1337/announce

udp://5.2.79.22:6969/announce

udp://95.211.168.204:2710/announce

http://51.68.122.172:80/announce

udp://210.244.71.25:6969/announce

udp://51.38.184.185:6969/announce
```
## 二、也可以使用安装网页版webui-aria2
1. 下载网页版webui-aria2
```
git clone https://github.com/ziahamza/webui-aria2.git
```
2. 打开运行
```
cd webui-aria2
```
3. 启动
```
node node-server.js
```
4. 输入提示的网址打开

当然以上图形化对于普通人是非常有好的，如果不想麻烦就直接使用命令下载更加方便。

## 也可以安装图形界面直接命令下载
* 命令下载
```
aria2c 链接
```
* 断点续传下载
```
aria2c -c 之前下载文件的链接
```
* 下载并修改文件名
```
aria2c -o 链接 文件名
```
* 下载多个文件
```
aria2c -Z 链接1 链接2
```
* 设置线程
```
aria2 -x 5 链接
```
分断下载
```
aria2 -s 16 url
```
多线程分断下载
```
aria2 -x16 -s 16 url
```