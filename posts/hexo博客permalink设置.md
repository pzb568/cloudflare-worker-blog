&emsp;&emsp; 网站搭建差不多2年了，没有设置过永久链接，所有的文章都是中文的以至于网站地址特别长，不方便记忆，不美观。利用**hexo-abbrlink**这个插件可以解决
# 安装hexo-abbrlink
```
npm install hexo-abbrlink --save
```
# 站点配置
```
permalink: post/:abbrlink.html
abbrlink:
  alg: crc32  # 算法：crc16(default) and crc32
  rep: hex    # 进制：dec(default) and hex
  ```
<escape><!-- more --></escape>
# 利用404跳转到主页
>由于网址方式了变成百度谷歌抓取的信息是之前网站信息，以至于正常无法方法可以利用404网页使打不开的网页回到主页，当然你需要点击**回我的主页**。
# 新建404页面
```
hexo new page 404
```
# 编辑404.md 
>添加Front-matter信息**permalink: /404**并替换自己的网站地址，下面的网址是腾讯公益信息宝贝回家，寻找失踪儿童的信息。
```
---
title: 404
date: 2018-11-08 21:19:51
permalink: /404
---
<script type="text/javascript" src="//qzonestyle.gtimg.cn/qzone/hybrid/app/404/search_children.js" charset="utf-8" homePageUrl="https://pzb568.github.io" homePageName="回到我的主页"></script>
```
下面你可以预览一下
https://pzb568.github.io/2018/11/09/v2ray%E7%9A%84%E4%BD%BF%E7%94%A8%E4%B8%8E%E5%88%86%E4%BA%AB/
>由于网站地址方式了变化，之前valine的数据地址不一样，所以所有的评论信息都会消失，请谨慎选择。