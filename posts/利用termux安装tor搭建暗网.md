
Tor简介
====
![](https://i.bmp.ovh/imgs/2019/04/07b5c785087abb9c.jpg)
&emsp;&emsp; Tor用户在本机运行一个洋葱代理服务器（onion proxy），这个代理周期性地与其他Tor交流，从而在Tor网络中构成虚电路（virtual circuit）。Tor是在5层协议栈中的应用层进行加密（也就是按照'onion'的模式）。而它之所以被称为onion，是因为它的结构就跟洋葱相同，你只能看出它的外表，而想要看到核心，就必须把它层层的剥开。即每个路由器间的传输都经过对等密钥（symmetric key）来加密，形成有层次的结构。它中间所经过的各节点，都好像洋葱的一层皮，把客户端包在里面，算是保护信息来源的一种方式，这样在洋葱路由器之间可以保持通讯安全。同时对于客户端，洋葱代理服务器又作为SOCKS接口。一些应用程序就可以将Tor作为代理服务器，网络通讯就可以通过Tor的虚拟环路来进行。用户通过它可以在因特网上进行匿名交流从而保护用户的隐私及资讯安全。
  termux可以安装tor在利用lighttpd服务器映射，下面来在termux里面安装。
<escape><!-- more --></escape>

# 1. 安装tor和lighttpd服务器
```
pkg in tor lighttpd 
```
# 2.编辑Torrc
```
cat > $PREFIX/etc/tor/torrc <<EOF
#Enable TOR SOCKS proxy
SOCKSPort 127.0.0.1:9050
#Hidden Service: Http
HiddenServiceDir /data/data/com.termux/files/home/.tor/hiddenservice
HiddenServicePort 80 127.0.0.1:8080
EOF
```
# 3.编写lighttpd配置文件
```
termux-setup-storage&&rm -rf ~/storage
cat > ~/lighttpd.conf <<EOF
server.port             = 8080
server.document-root    = "/sdcard/Orweb"
server.upload-dirs      = ( "/data/data/com.termux/files/usr/tmp" )
index-file.names        = ( "index.html" )
mimetype.assign         = (
                                ".html" => "text/html",
                                ".txt" => "text/plain",
                                ".css" => "text/css",
                                ".js" => "application/x-javascript",
                                ".jpg" => "image/jpeg",
                                ".jpeg" => "image/jpeg",
                                ".gif" => "image/gif",
                                ".png" => "image/png",
                                "" => "application/octet-stream"
                       )
EOF
```
# 4.启动Orweb-daemon
```
mkdir -p /sdcard/Orweb
```
# 5.启动lighttpd服务器
```
lighttpd -f ~/lighttpd.conf& > /dev/null
```
# 6.启动Tor
重新打开一个窗口
```
tor
```
# 7. 查看域名
* 等待tor连接到主服务器并完成初始化(bootstrap)，然后新开一个termux会话，执行如下命令查看域名
```
echo "Onion域名:$(cat ~/.tor/hiddenservice/hostname)"
```
* 挂载[Shadowsocks](https://pzb568.github.io/2018/11/08/ss%E7%B3%BB%E5%88%97%E8%BD%AF%E4%BB%B6%E5%88%86%E4%BA%AB%E5%8F%8A%E4%BD%BF%E7%94%A8/)或者[v2ray](https://pzb568.github.io/2018/11/09/v2ray%E7%9A%84%E4%BD%BF%E7%94%A8%E4%B8%8E%E5%88%86%E4%BA%AB/)，访问暗网必须要tor ，国内因为你懂的原因必须要梯子。

* 给网站添加内容，用[Mnote](https://www.coolapk.com/apk/com.hjq.md)写一份Markdown文档，转换为html，命名为index.html放到/sdcard/Orweb目录，网站内容自己编写。

## 错误处理

如果没有成功或者报错删除.tor文件夹
```
rm -rf .tor
```
再次启动服务器和tor继续第五第六步

# 8 . 测试网站
1. 下载最新版Torhttps://www.torproject.org/download/#android 选择arm版或者谷歌市场下载。
2. 打开Tor browser连接成功后输入上面第7步查看到域名地址，然后就可以看到你的暗网网站了。

