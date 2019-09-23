&emsp;&emsp; Jupyter notebook（又称 IPython notebook），支持运行超过 40 种编程语言。Python 的一个强大的模块, 成功安装的话可以实现比caddy的效果, 支持web下的终端操作, 支持代码高亮运行。
<escape><!-- more --></escape>
# Jupyter notebook安装
1. 安装python 编译库
```
pkg install python
pkg install python-dev
```
2. 用python封装包安装
```
pip install jupyter
```
3. 启动
```
jupyter notebook
```
如下图
复制最下面的网址到浏览器
![](1.jpg)
然后就可以开始尽情的玩耍了
![](2.jpg)
# Jupyter notebook卸载
使用**pip uninstall jupyter**是无法卸载的必须使用下面方法。
```
pip install pip-autoremove
pip-autoremove jupyter -y
```