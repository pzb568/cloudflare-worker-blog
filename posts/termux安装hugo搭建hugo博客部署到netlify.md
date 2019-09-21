# termux安装hugo
```
apt install hugo
```
# 新建网站
```
hugo new site blog
```
# 主题配置

1. 进入网站根目录
```
cd blog
```
2.下载子模主题
```
git submodule init https://github.com/olOwOlo/hugo-theme-even themes/even
```
3. 配置主题请参考官方主题设置

重要: 在主题的 exampleSite 目录下有一个 config.toml 文件，将这个 config.toml 文件复制到你的站点目录下，根据自己的需求更改即可。
```
cp themes/even/exampleSite/config.toml ~
```
注意: 对于这个主题，你应该使用 post 而不是 posts，即 hugo new post/some-content.md。

4. 启动本地服务器
```
hugo server 
```

# netlify配置文件

要部署到netlify，必须建一个netlify配置文件,可以参考
https://gohugo.io/hosting-and-deployment/hosting-on-netlify/
1. 在网站根目录
```
vim netlify.toml
```
输入如下内容
```
[build]
publish = "public"
command = "hugo --gc --minify"

[context.production.environment]
HUGO_VERSION = "0.55.6"
HUGO_ENV = "production"
HUGO_ENABLEGITINFO = "true"

[context.split1]
command = "hugo --gc --minify --enableGitInfo"

[context.split1.environment]
HUGO_VERSION = "0.55.6"
HUGO_ENV = "production"

[context.deploy-preview]
command = "hugo --gc --minify --buildFuture -b $DEPLOY_PRIME_URL"

[context.deploy-preview.environment]
HUGO_VERSION = "0.55.6"

[context.branch-deploy]
command = "hugo --gc --minify -b $DEPLOY_PRIME_URL"

[context.branch-deploy.environment]
HUGO_VERSION = "0.55.6"

[context.next.environment]
HUGO_ENABLEGITINFO = "true"
```

<!--more-->

# 上传源代码

1. 进入博客目录
```
cd blog
```
2. 创建版本库
```
git init
```

3. 在[github](https://www.github.com)或者[gitee](https://www.gitee.com)新建一个仓库blog

4. 生成ssh密匙
>如果已经设置ssh密钥，直接跳到下一步
```
ssh-keygen -t rsa -C "你github登录邮箱"
```
直接回车3次生成成功
```
cat .ssh/id_rsa.pub
```
复制内容添加到github ssh密匙中。


4. 连接到远程库
```
git remote add origin https://gitee.com/xxx/blog.git
```
9. 添加全部博客文件

```
git add -A
```

10. 注释
```
git commit -m "hugo博客"
```

11. 第一次部署强制上传到服务器
```
git push -u origin master
```

12. 以后在更新直接更新
```

git push origin master
```
# 部署网站到netlify

1. 进入[netlify]()网站点击github如下图
![](https://i.bmp.ovh/imgs/2019/07/f6060b926a15ab9e.png)
2. 选择上面github仓库，配置成功后自动生成网站。
3. 修改netlify域名及解析自己的域名并开启https  
>netlify自动生成的域名不方便记忆，修改后netlify的域名是https://www.****.netlify.com
所有的配置都在setting下面

![](https://i.bmp.ovh/imgs/2019/07/a1aad731f1137789.png)
