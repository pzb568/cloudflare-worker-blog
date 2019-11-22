
&emsp;&emsp; WireGuard是国外开发的一个高速翻墙工具，没有中文，但是非常简单好用，现在推荐给大家
1.注册AzireVPN账号：https://www.azirevpn.com/manager/auth/login，只需要填写用户名USERNAME和密码PASSWORD即可，可以不填Email，这才是注重隐私的VPN供应商
~~2.下载配置文件：https://www.azirevpn.com/cfg/wireguard，在这个网址填写注册的用户名密码，点Download Configuration。目前提供了加拿大多伦多(azirevpn-ca1)，西班牙马拉加(azirevpn-es1)，瑞典斯德哥尔摩(azirevpn-se1)，英国伦敦(azirevpn-uk1)，美国迈阿密(azirevpn-us1)这5个节点~~之前有免费体验，现在只能购买了。
<escape><!-- more --></escape>
3.
安装WireGuard Android客户端，Play下载地址：https://play.google.com/store/apps/details?id=com.wireguard.android
4.导入配置文件：把之前下载的配置文件传到手机里，手机上打开WireGuard客户端，点右下角加号，选择第一个Create from file or archive，点选传到手机里的配置文件。这时直接点选某个配置文件即可连接VPN，建议选择uk1服务器
5.WireGuard客户端可以允许部分应用绕过VPN，打开WireGuard，点击一个节点配置，在右上角点击铅笔按钮，在中间有蓝色的0 EXCLUDED APPLICATIONS，点击后进入APP排除设置，勾选某个APP就是让这个APP不走VPN通道。选择完成后点右下角蓝色SET EXCLUSIONGS，然后点配置界面右上角的保存按钮即可。
6.WireGuard Android客户端支持快捷设置面板功能。即在下拉通知栏中可以添加WireGuard快捷设置