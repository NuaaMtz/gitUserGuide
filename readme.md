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
清空了.


