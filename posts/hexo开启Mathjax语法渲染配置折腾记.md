---
title: hexo开启Mathjax语法渲染配置折腾记
comments: true
tags:
  - hexo配置
  - 开启mathjax  Latex
  - 数学公式
  - 化学工式
  - 主题样式
categories:
  - 软件应用
mathjax: true
abbrlink: 97f2042f
date: 2019-04-30 23:25:52
---

Mathjax介绍
====
&emsp;&emsp; hexo默认的渲染器是marked，并不支持mathjax。kramed是在marked基础上修改的，支持了mathjax。在的hexo工程目录下的node_modules中可以找到对应的渲染器文件夹。同时在你的工程目录下用以下命令安装kramed。另外补充一个NexT配置中推荐的渲染器hexo-renderer-pandoc，功能很强大不仅可以渲染markdown，还支持textile、reStructedText等许多其他格式
# 安装渲染器
## 卸载默认渲染器
```
npm uninstall hexo-renderer-marked --save
```
## 安装修改kramed渲染器
```
npm install hexo-renderer-kramed --save
```
或者`npm install hexo-renderer-pandoc --save`如果是在安卓手机termux里面部署网站这个插件不能使用，因为必装`pandoc`，termux安装pandoc不成功。

# 安装**hexo-renderer-mathjax**插件

如果安装了hexo-math插件，需要卸载再安装。
## 卸载hexo-math插件
```
npm uninstall hexo-math --save
```
## 安装
```
npm install hexo-renderer-mathjax --save
```
## CDN加速

>更新mathjax的CDN链接，打开node_modules/hexo-renderer-mathjax/mathjax.html

```
<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML"></script>
```


# 主题配置

math:
  enable: true #开启

  engine: mathjax 取消注释

# 文章Front-matter中开启mathjax
```
---
title: 
category:
date: 
mathjax: true  #开启后才会渲染数学公式
---
```
<escape><!-- more --></escape>

# 测试

下面来测试一下

##麦克斯韦方程组
```
$$
\begin{eqnarray}
\nabla\cdot\vec{E} &=& \frac{\rho}{\epsilon_0} \\
\nabla\cdot\vec{B} &=& 0 \\
\nabla\times\vec{E} &=& -\frac{\partial B}{\partial t} \\
\nabla\times\vec{B} &=& \mu_0\left(\vec{J}+\epsilon_0\frac{\partial E}{\partial t} \right)
\end{eqnarray}
$$
```

$$
\begin{eqnarray}
\nabla\cdot\vec{E} &=& \frac{\rho}{\epsilon_0} \\
\nabla\cdot\vec{B} &=& 0 \\
\nabla\times\vec{E} &=& -\frac{\partial B}{\partial t} \\
\nabla\times\vec{B} &=& \mu_0\left(\vec{J}+\epsilon_0\frac{\partial E}{\partial t} \right)
\end{eqnarray}
$$

```
$$\Gamma(z) = \int_0^\infty t^{z-1}e^{-t}dt\,.$$
```

$$\Gamma(z) = \int_0^\infty t^{z-1}e^{-t}dt\,.$$

```
$$
\frac{\partial u}{\partial t} = h^2 \left( \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} + \frac{\partial^2 u}{\partial z^2}\right)
$$
```

$$
\frac{\partial u}{\partial t} = h^2 \left( \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} + \frac{\partial^2 u}{\partial z^2}\right)
$$

```
 $$ 
f(n)=\begin{cases}
n/2, & \text{如果$ x<=2 $}\\
3n+1, & \text{如果$ x>2 $}
\end{cases}
$$
```

 $$ 
f(n)=\begin{cases}
n/2, & \text{如果$ x<=2 $}\\
3n+1, & \text{如果$ x>2 $}
\end{cases}
$$

```
$\ce{CO2 + C -> 2 CO}$
```

$\ce{CO2 + C -> 2 CO}$

```
$\ce{H2O}$
```

$\ce{H2O}$

```
$\ce{2 H2O}$
```

$\ce{2 H2O}$
```

$\ce{A <=>> B}$
```

$\ce{A <=>> B}$

```
$\ce{CH4 + 2 $\left( \ce{O2 + 79/21 N2} \right)$}$
```

$\ce{CH4 + 2 $\left( \ce{O2 + 79/21 N2} \right)$}$

标题Latex特性测试
----
1. Setext 形式
----
```
H1
====

H2
----
```
H1
====

H2
----

= 和 - 的数量是没有限制的。通常的做法是使其和标题文本的长度相同，这样看起来比较舒服。或者可以像我一样，用四个 - 或 =。
Setext 形式只支持 h1 和 h2 两种标题。

2. atx 形式
 #####① 可以用对称的 # 包括文本：#####
```
####H4####

#####H5#####
```
####H4####

#####H5#####


##### ② 也可以只在左边使用 #：
```
####H4

#####H5
```
####H4

#####H5


③ 成对的 # 左侧和只在左边使用的 # 左侧都不可以有任何空白，但其内侧可以使用空白。
```
 ###左侧使用了空格###

#### 内侧使用了空格
```
 ###左侧使用了空格###

#### 内侧使用了空格
