---
title: Markdown编辑器日常使用语法记录
comments: true
tags:
  - hexo
  - Markdown
  - 语法
  - 段首缩进
  - 文本居中
  - 音乐播放
  - 视频播放
  - 飘向北方
  - Despacito
categories:
  - 软件工具
abbrlink: 4703653d
date: 2019-05-29 21:33:04
description:
---
&emsp;&emsp; Markdown是一种可以使用普通文本编辑器编写的标记语言，通过简单的标记语法，它可以使普通文本内容具有一定的格式。
&emsp;&emsp; hexo默认支持Markdown编辑文章，学习好Markdown 编辑器语法有利于更方便友好的写作;下面我会用一些事例分享Markdown 编辑器使用中的各种技巧。
## 段首缩进
> 在文章编辑排版中首先经常使用到的就是段首缩进；那可以看到我的大标题是有缩进使用技巧非常简单就是在段道输入如下代码
```
&emsp;&emsp;
```
下面用菜根谭中一段做例
&emsp;&emsp; 好丑心太明，则物不契；贤愚心太明，则人不亲。士君子须是内精明而外浑厚，使好丑两得其平，贤愚共受其益，才是生成的德量。
# 标题
>标题我在之前的文章中己有教程，具体可以跳转[hexo开启Mathjax语法渲染配置折腾记](https://pzb568.github.io/2019/04/30/Mathjax%E8%AF%AD%E6%B3%95%E6%B8%B2%E6%9F%93/)这里查看。

# 文本局中
> 在诗词歌曲中使用局中显示，可以更好的显示诗词的排版，看起来更加工整。  
+ 使用也非常简单代码如下
```
{% cq %}
夜宿山寺 
唐 · 李白
危楼高百尺，手可摘星辰。
不敢高声语，恐惊天上人。
{% endcq %}
```
下面用唐诗一首演示

{% cq %}
夜宿山寺 
唐 · 李白
危楼高百尺，手可摘星辰。
不敢高声语，恐惊天上人。
{% endcq %}
# 插入图片
>可以插入网络中和本的的图片
```
![](images/1.jpg)
```
美女图片镇楼
![](https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1559150762962&di=89f86d08e03074713a0d4f9114f9b9ec&imgtype=0&src=http%3A%2F%2Ft9.baidu.com%2Fit%2Fu%3D3210444378%2C1295390531%26fm%3D193)
# 分页显示
>哦😊到这里应该要分页了
代码如下
```
<escape><!-- more --></escape>
```
<escape><!-- more --></escape>

# 链接
1. 文字链接
```
[github](www.github.com)
```
[github](www.github..com)
2. 网址链接
www.Google.hk

# 插入音乐
1. 安装
在blog文件夹下安装**hexo-tag-aplayer**插件

```
npm install --save hexo-tag-aplayer
```
2. 使用
代码如下
```
{% aplayer "飘向北方" "黄明志,王力宏" "http://music.163.com/song/media/outer/url?id=461864856.mp3" "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1559501443630&di=5d355fdbb782fb5bc06c476af70ba19a&imgtype=0&src=http%3A%2F%2Fsource.upupoo.com%2Ftheme%2F1800037383%2FpreviewFix.jpg" "lrc:lrc.txt" %}
```
**欣赏音乐飘向北方-黄明志&王力宏**
{% aplayer "飘向北方" "黄明志,王力宏" "http://music.163.com/song/media/outer/url?id=461864856.mp3" "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1559501443630&di=5d355fdbb782fb5bc06c476af70ba19a&imgtype=0&src=http%3A%2F%2Fsource.upupoo.com%2Ftheme%2F1800037383%2FpreviewFix.jpg" "lrc:lrc.txt" %}

[^_^]: # ({% aplayer "Despacito" "Luis Fonsi,Daddy Yankee" "http://music.163.com/song/media/outer/url?id=452613551.mp3" "https://cn.bing.com/th?id=OIP.gwgvhtMZN0GoZhZQ63OPhgAAAA&pid=Api&dpr=2.62" %})

# 插入视频
1. 安装  
```
npm install --save hexo-tag-dplayer
```
2. 使用
输入 如下代码
```
{% dplayer "url=https://vodkgeyttp8.vod.126.net/cloudmusic/YCEhICAiIWI1ISAxMSEiMA==/mv/5617127/36fb72932c6a0682fe09f201e2fdda0b.mp4?wsSecret=bd2a79912d92c40a0557933e82a43f57&wsTime=1562298067"  "pic=http://p1.music.126.net/xrLKWowydpr7W_g8YgKBRQ==/18730180580875994.jpg" "loop=yes" "theme=#FADFA3" "autoplay=false" "token=tokendemo" %}
```
**欣赏视频Despacito-DaddyYankee&Luis Fonsi**
{% dplayer "url=https://vodkgeyttp8.vod.126.net/cloudmusic/YCEhICAiIWI1ISAxMSEiMA==/mv/5617127/36fb72932c6a0682fe09f201e2fdda0b.mp4?wsSecret=bd2a79912d92c40a0557933e82a43f57&wsTime=1562298067"  "pic=http://p1.music.126.net/xrLKWowydpr7W_g8YgKBRQ==/18730180580875994.jpg" "loop=yes" "theme=#FADFA3" "autoplay=false" "token=tokendemo" %}
# 表格
```
| 姓名 | 性别 | 电话 |
| :--- | :----: | ----: |
| 张三 | 男 | 123456789123 |
```
| 姓名 | 性别 | 电话 |
| :--- | :----: | ----: |
| 张三 | 男 | 123456789123 |












