&emsp;&emsp; 在添加 Hexo 博客 加密功能的模块有2个，一个是hexo-blog-encrypt，另一个是hexo-encrypt。可任选一个。
# hexo-blog-encrypt插件
## 安装hexo-blog-encrypt插件
```
npm install --save hexo-blog-encrypt
```
## 配置启用插件
```
# Security
encrypt: # hexo-blog-encrypt
  enable: true
  ```
## 加密文章
```
  ---
title: Hello World
date: 2016-03-30 21:18:02
password: 123456  #密码
abstract: Something was encrypted, please enter password to read.  #摘要
message: Welcome to my blog, enter password to read. # 描述性文字
---
```
<escape><!-- more --></escape>

# hexo-encrypt插件
##  安装
```
npm install hexo-encrypt --save
```
## 博客设置**_config.yml**添加
```
# encrypt
  encrypt:     
  pwdfile: encrypt_password
```
## 在需要加密的文章上添加
```
---
title: hexo博客加密设置
tags:
  - 加密模板
categories:
  - hexo加密
comments: true
mathjax: false
date: 2019-07-05 02:31:41
encrypt: true 
enc_pwd: 123456 #设置的密码
---
```



