You-Get简单介绍
====
&emsp;&emsp; [you-get](https://github.com/soimort/you-get/wiki/%E4%B8%AD%E6%96%87%E8%AF%B4%E6%98%8E)是一个基于 Python 3 的下载工具。使用 You-Get 可以很轻松的下载到网络上的视频、图片及音乐。
# 一、安裝
----
## 1.更新

```
pkg update && pkg upgrade
```
## 2.获取SD卡读写权限
```
termux-setup-storage
```
## 3.安装python ffmpeg##

```
pkg install python ffmpeg
```
## 4. __升级__版本 pip版本
```
python -m pip install --upgrade pip
```
## 4. 安装you-get
```
pip install you-get
```
## 5. 更新you-get
```
pip install --upgrade you-get
```
<escape><!-- more --></escape>
----
# 二、you-get使用
 查看**版本 **
 ```
you-get -V  
```
 查看__视频信息 __ 
下面我测试一下西虹市首富
 ```
you-get -i http://m.iqiyi.com/v_19rrf2nw1g.html
 ```
 ![](01.jpg)
 
**解析**
```
you-get -u http://m.iqiyi.com/v_19rrf2nw1g.html
```
![](02.jpg)
**下载 **
```
you-get -o /sdcard/video/ http://m.iqiyi.com/v_19rrf2nw1g.html
```
![](03.jpg)
you-get的功能非常的多，如果你想了解you-get的所以使用方法可以去github [you-get](https://github.com/soimort/you-get/wiki/%E4%B8%AD%E6%96%87%E8%AF%B4%E6%98%8E) 项目里面查看，里面有详细使用方法，这里就简单的介绍到这里了。
下面附一个网上简单的视频，有助于更快更简单的使用you-get。
<iframe src="//player.bilibili.com/player.html?aid=24822266&cid=41834559&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

