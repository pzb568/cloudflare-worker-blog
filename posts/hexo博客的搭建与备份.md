
# 一、搭建
====
&emsp;&emsp; Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。hexo 博客在Linux系统中搭建是非常简单的，在WIN系统中比较复杂，我们接触的手机📱永远要比电脑的时间要多那么我们可以在安卓手机上使用termux来搭建，这样随时随地都可以写做和发表文章。
## 1. 下载termux##
1. 下载termux可以在谷歌商店里面下载，但是想要进入谷歌商店需要翻墙，想了解翻墙教程可以去看一下我之前的文章[ss系列软件分享及使用](https://pzb568.github.io/2018/11/08/ss%E7%B3%BB%E5%88%97%E8%BD%AF%E4%BB%B6%E5%88%86%E4%BA%AB%E5%8F%8A%E4%BD%BF%E7%94%A8/) [v2ray的使用与分享](https://pzb568.github.io/2018/11/09/v2ray%E7%9A%84%E4%BD%BF%E7%94%A8%E4%B8%8E%E5%88%86%E4%BA%AB/)或者直接下载网盘分享的termux。 点击[下载](https://www.lanzous.com/i4935gh)
2. 进入并更新termux，第一次进入需要等几分钟出现命令界面然后输入
```
pkg update
```
如果感觉键位太少可以看之前的文章[修改添加常用键](https://pzb568.github.io/2019/02/26/termux0.66%E6%B7%BB%E5%8A%A0%E5%B8%B8%E7%94%A8%E6%8C%89%E9%94%AE/)
## 2. 安装必须组件和hexo ##
1. 安装 nodejs git openssh必须软件
```
pkg install nodejs git openssh
```
2. 安装hexo
```
npm install hexo-cli -g
```
3. 初始化新建一个叫blog的文件夹
```
hexo init blog
```
4. 进入blog文件夹
```
cd blog
```
5. 安装npm 核心组件支持
```
npm install
```
## 3. 下载主题并配置 ## 
1. 下载主题，hexo的主题非常丰富可以去[官方主题](https://hexo.io/themes/)下载；下面有演示我使用的主题[next](https://github.com/theme-next/hexo-theme-next)
```
git clone https://github.com/theme-next/hexo-theme-next themes/next
```
2. 在站点配置文件_config.yml开启next主题可以下载[quickedit](https://www.lanzous.com/i3w2y0b)来编辑打开位于/data/data/com.termux/files/home/blog文件夹下_config.yml文件查找**theme:**修改theme: 空格next。具体的站点和主题信息配置请自行去[hexo](https://hexo.io/zh-cn/)和[next主题](http://theme-next.iissnan.com/)文档查看
3.  启动本地服务器查看
```
hexo server
```
## 4 . 配置ssh密钥及github或者gitee部署##
1. 先成**ssh-keygen**密钥
```
ssh-keygen
```
2. 注册[gitee](www.gitee.com)或者[github](www.github.com)帐号并新建一分项目。gitee项目名即是网站域名部署成功后需要开启gitee page；github项目名为用户名.github.io部署成功后https://用户名.github.io会自动生命github page。
3. 复制ssh公钥到新建的[gitee](www.gitee.com)或者[github](www.github.com)帐号的设置里面ssh密钥并保存。
```
cat .ssh/id_rsa.pub
```
4. 验证ssh是否连接成功
1. gitee帐号验证
```
ssh -T git@gitee.com
```
2. github账号验证
```
ssh -T git@github.com
```
## 5. 生成及部署 
1. 清理缓存
```
hexo clean
```
2. 生成
``` 
hexo generate
```
3. 部署
```
hexo deploy
```
可以简化一步执行
```
hexo clean && hexo g -d
```


# 二、备份
   经常在多个平台写博客，或者经常重新安装统、在安卓手机termux里面使用hexo经常刷机，会导致博客及配置文件的的丢失，我的这个博客也丢失了很多次了，最后我想了个办法利用github来备份博客的文件和数据，这样博客的文件和数据永远不会弃失，并且还可以在多个平台同时发布文章。

1. 在github新建一个叫blog的仓库
2. 在本地博客文件夹创建git版本库，如果有安装git必须先安装git

1. 安卓termux 安装git
```
pkg install git
```
2. Ubuntu安装git
```
apt install git
```
3. archLinux安装git
```
pacman -S git
```
3. 进入需要备份blog目录
```
cd ~
cd blog
```
4. 创建版本库
```
git init
```
<escape><!-- more --></escape>
这个时候blog的版本库已经创建好了。
验证是否成功，如果有一个.git的隐藏文件就说明创建成功。
查看隐藏文件
```
ls -a
```
5. 在github 或者gitee创建项目仓库
6. 连接上面github创建的仓库
```
git remote add origin git@github.com:you name/blog.git
```
7. 添加备份文件source/ themes/ _config.yml scaffolds/ package.json .gitignore 这些文件需要备份
```
git add source/ themes/ _config.yml scaffolds/ package.json .gitignore
```
8. 注释备份内容，明确的注释可以回退版本
```
git commit -m "博客备份"
```
9. 第一次强制上传文件到github仓库
```
git push -u origin master
```
这样博客就备份成功了，之后备份直接前面3 `4步，第5部直接使用下面命令就可以了
```
git push origin master
```
# 三、恢复

## 1. 安装博客必要组件
1. 安装coreutils
```
pkg install coreutils
```
2. 安装git
```
pkg install git
```
3. 安装node.js
```
pkg install nodejs
```
4. 安装hexo 
```
npm install hexo-cli -g
```
## 2. git clone自己备份的博客源代码克隆备份的bolg源文件地址是你自己的地址这里不做演示
```
git clone <版本库的网址> <本地目录名> 
```
1. 进入bolg文件夹并安装hexo
```
cd bolg
npm install hexo-cli -g
```
2. 安装npm 组件
```
npm install
```
## 3. 安装插件
1. 安装deployer-git 
```
npm install hexo-deployer-git --save
```
2. 安装搜索功能插件
```
npm install hexo-generator-searchdb --save
```
3. 安装Valine评论系统
```
npm install valine --save
```
4. 文字统计插件
```
npm install hexo-symbols-count-time --save
```
5. 音乐插件
```
npm install --save hexo-tag-aplayer
```
6. 视频插件
```
npm install hexo-tag-dplayer --save
```
搞定希望这个教程对你有所帮助。



