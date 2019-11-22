
&emsp;&emsp; 由于next主题经常更新，自己又在本地大量修改主题，更新中会有很多问题，经过很多次折腾及网络上其他朋友的教程，我找到了不错的处理方法。
1. 进入主题目录并更新
```
cd themes/next
git pull
```
因为修改了很多的配置项目，所以更新失败了
<escape><!-- more --></escape>
2. 将修改储藏到暂存区
我们可以通过`git stash`这句命令将对主题文件的修改储存到本地的暂存区：
```
git stash
```
3. 执行更新
我们现在需要再次使用 git pull 命令来获取最新的主题文件，别担心，这次不会再有上面的错误了
```
git pull
```
4. 从暂存区取出修改
我们现在要通过执行 **git stash pop** 这句命令来从暂存区取出修改。
```
git stash pop
```
如果报错如下内容需要进入提示的文件修改
```
$ git stash pop
Auto-merging _config.yml
CONFLICT (content): Merge conflict in _config.yml
```
5. 进入文件
可以看到文中<<<<<<HEAD，=======中间是上游分支，======，>>>>>>b8e436中间是你自己的分支，删掉一个就可以了
6. 提交记录
```
git add _config.yml
git commit -m "冲突处理"
```
7. 在更新
```
git pull
```
主题升级成功。
