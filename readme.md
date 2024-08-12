# 这个文档是用来自己用的教自己怎么用github的仓库

1. 初始化
就是将文件夹标记为是一个项目

```shell

git init

```
运行完之后,无论文件夹是不是空,该项目都是空的,因此要添加


2. 添加文件
```shell
git add readme.md

```
或者是全部都添加
```shell
git add .

```
这样就将文件标记为仓库里面的文件了

3. 提交
将标记的文件真正进行保存为一个项目的一个版本
```shell
git comment -m "This is comments for this version"
```

这里引入工作区和暂存区的概念:
()[./gitadd.png]
工作区就是当前文件.暂存区就是add命令运行后把工作区的内容推送到的地方.
()[./gitcomments.png]
当运行comments命令后,就是把暂存区的内容移动到一个分支上的一个版本上,形成一个版本.此时暂存区的内容就
清空了.关于分支,当不自定义的时候,只走上面两步的情况下,git自动生成一个唯一的名为master的分支

4. 忽略特定文件
忽略某些文件/文件夹:在根目录下创建.gitignore文件,在里面填写忽视的文件文件
文件夹要以/开头

5. 远程仓库
远程仓库就是在前面的过程后面再加一个网络的分支
首先是要先在github上创建仓库
然后将本地的分支关联到远程的分支,网络的仓库一般习惯性认为设置为origin,来源,一看就是远程的仓库
```shell
git remote add origin git@github.com:michaelliao/learngit.git

```
最后将本地仓库的文件推送到远程仓库,我们上面所说,默认生成的分支名为:master

```shell
git push -u origin master

```
首次运行加上u参数,是为了完成关联,之后可以不需要加参数

6. 添加密钥
如果真是从零开始,push是不能推送成功的,因为电脑不知道这是不是你的账号.
生成私钥和公钥,公钥放在github上,私钥放在本地电脑的~/.ssh
参考文献:
www.cnblogs.com/liyan-blogs/p/15153764.html


7. 修改为https上传
```shell
git remote set-url origin https.......(仓库的htpps地址)

git config --global --unset http.proxy
git config --global --unset https.proxy

```
8. 加速访问


绕过DNS域名解析会明显提高速度

9. 明文保存密码
因为国内网络问题,ssh之类的方法不好用,所以下下策明文保存
```shell
git config --global credential.helper store

```
