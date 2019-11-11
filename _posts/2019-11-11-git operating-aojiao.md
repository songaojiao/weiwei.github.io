---
layout: post
title: 了解Git
summary: Markdown is a way to style text on the web.
featured-img:  emile-perron-190221
---


<p style="font-size:53px;text-align:center">Git	笔记</p>
## **Git 说明**

#### 		就是一个帮我们管理文件版本的程序, 专业名称叫 : <b style="color:red">分布式版本控制系统</b>

`https://www.liaoxuefeng.com/wiki/896043488029600/898732864121440` 资料来源



### 什么是版本控制系统
​		版本控制就是帮我们完成上面操作的系统或者说就是一个应用程序



### 版本控制系统如何帮我们控制版本?

​		我们需要进行版本控制 的文件都要提交到一个** 仓库 (一个隐藏文件夹) **里面, 我们对文件做出的修改都会被这个版本控制系统侦测到, 如果我们要保留这个版本的文件,就要通过版本控制系统提供的命令把文件提交到仓库里面,然后版本控制系统就会自动为我们提交的文件打上版本号
​		<b style="font-size:23px;color:red">我理解的是每次修改都会将这次修改记录下来,方便查看和寻找</b>



### 仓库分为几种


1. 本地仓库 : 建立在本地的文件夹
2. 远程仓库 : 建立在互联网的服务器内的文件夹 GitHub 还有Gitee(码云)



### 版本控制系统分为几种?


#### 1. 分布式版本系统控制
   1. 配有上述两个仓库, 在你的<b style="font-size:18px">电脑上有一个本地仓库</b>, 在远程的<b style="font-size:18px">服务器上有一个远程仓库.</b>
   2. 我们在提交文件的时候会<b style="font-size:18px">先提交到本地仓库</b>, 然后在有网络的情况下, <b style="font-size:18px">再从本地仓库提交到网络上的远程仓库</b>.
   3. <b style="font-size:16px;color:#f1e">Git就是一天典型的分布式版本控制系统</b>

#### 2. 集中式版本控制系统
1. 只配有上述的远程仓库, 当然如果你的这台电脑就充当远程服务器的角色,那远程仓库	其实就在你这台电脑上.
2. 我们在提交文件的时候是<b style="font-size:18px">直接提交到远程仓库</b>
3. <b style="font-size:16px;color:#f1e">SVN 就是一个典型的集中式版本控制系统</b>



## **安装Git**

**sudo apt -get install git**			通过一条就可以直接完成Git的安装

<https://git-scm.com/downloads>			可以从官网下载Git安装包进行安装

#### 安装完以后进行设置

1. git config --global user.name "Your Name"		配置用户名
2. git config --global user.email "email@example.com"		配置邮箱

git config	命令的	--global	参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置





### 了解Git
#### 1. 仓库 (Repository)

   受版本控制的所有文件修订历史的共享数据库

#### 2.  工作空间 (Workspace)

   本地硬盘或Unix 用户账户上编辑的文件副本

#### 3.  工作树/区 (Working tree)

   工作区中包含了仓库的工作文件. 可以修改的内容和提交更改做为新的提交到仓库

#### 4.  暂存区 (Staging area)

​	暂存区是工作区用来提交更改 (commit) 前可以暂存工作区的变化

​	`git add` 其实就是将文件放入暂存区,还没添加的状态
​	`git commit` 把暂存区中所有的内容提交到当前分支




![](https://images2017.cnblogs.com/blog/63651/201709/63651-20170904202237913-177051853.png)

#### 5.  索引 (Index)

​	索引是暂存区的另一种术语

术语|介绍
--|--
签入 checkin|将新版本复制回仓库
签出checkout|从仓库中将文件的最新修订版本复制到工作空间
提交 commit|对各文件的工作副本做了更改, 并讲这些更改提交到仓库 
冲突 conflict|多人对同一文件的工作副本进行更改, 并讲这些更改提交到仓库
合并 merge|将某分支上的更改联接 到此主干或同为主干的另一个分支
分支 branch|从主线上分离开的副本, 默认分支叫master
锁 lock|获得修改文件的专有权限
头 HEAD|头是一个象征性的参考, 最常用以指向当前选择的分支
修订 revision|表示代码的一个版本状态. Git通过用SHA1 hash算法表示的ID来表示不同的版本.
标记 tags|标记指的是某个分支某个特定时间点的状态. 通过标记,可以很方便的切换到标记时的状态

### 常见的版本控制器

#### 主流的版本控制器又如下这些:

* Git

* SVN (Subversion)

* CVS (Concurrent Versions System)

* VSS (Micorosoft Visual SourceSafe)

* TFS (Team Foundation Server)

* Visual Studio Online

  

  版本控制产品非常的多 （Perforce、Rational ClearCase、RCS（GNU Revision Control System）、Serena Dimention、SVK、BitKeeper、Monotone、Bazaar、Mercurial、SourceGear Vault) , 现在形象力最大且使用最广泛的是Git 和 SVN

### 工作流程

#### git 的工作流程一般是这样的:
1. 在工作目录中添加、修改文件;
2. 将需要进行版本管理的文件放入暂存区域;
3. 将暂存区的文件提交到git仓库。

  #####  因此, git管理的文件有三种状态 : 已修改 (codified) , 已暂存 (staged) , 已提交(commit)



###  版本退回

输入 `git log`  命令显示  从最近到最远的提交日志,我们可以看到3次提交

如果嫌输出信息太多, 看到眼花缭乱的, 可以试试加上 `--pretty=oneline` 参数:

`$ git log --pretty=oneline`   

显示的信息里面会有一大串类似`1094ad31d11f` 的这种数字 是`commit id` (版本号)

在Git中 用HEAD 表示当前版本, 上一个版本是`HEAD^`, 上上一个版本是`HEAD^^`, 往上100个版本	写成`HEAD~100`

将当前版本回退到上一个版本  可以使用命令`git reset` 命令:

`$ git reset --hard HEAD^`  

`$ git reset --hard cf40f1df04d9`  也可以使用这种指定跳到版本,版本号都是唯一的 版本号也可以只写前几位,Git会自动去寻找,但不能只写一两位

退回版本的时候顺便会把工作区的文件更新了, 所有你让`HEAD`指向那个版本号,当前版本就定位在那

`git reflog` 用来纪律每一个命令, 可以输入查找记录从而得知所有版本的版本号 

`(版本号) HEAD@{n}: commit: '提交说明' `,根据提交说明来寻找需要的版本号

#### 小结:

* `HEAD`指向的版本就是当前版本，Git允许我们在版本的历史之间穿梭，使用命令`git reset --hard commit_id`。
* 穿梭前，用`git log`可以查看提交历史，以便确定要回退到哪个版本。
* 要重返未来，用`git reflog`查看命令历史，以便确定要回到未来的哪个版本。





## 了解工作区和暂存区



### 工作区 (Working Directory)

就是在电脑能看到的目录, 选择的文件夹就是一个工作区

### 版本库 (Repository)

工作区又一个隐藏目录 `.git` , 这个不算工作区 , 指的是Git的版本库

Git的版本库里寸了很多东西, 其中最重要的就是称为stage (或者叫 index ) 的暂存区, 还有Git为我们自动创建的第一分支 master  , 以及master的一个指针叫 HEAD

前面讲了我们把文件往Git版本库里添加的时候，是分两步执行的：

第一步是用`git add`把文件添加进去，实际上就是把文件修改添加到暂存区；

第二步是用`git commit`提交更改，实际上就是把暂存区的所有内容提交到当前分支。



### 学习使用Git 仓库

| 输入                     | 作用                           |
| ------------------------ | ------------------------------ |
| git init                 | 初始化仓库                     |
| vim 文件名  touch 文件名 | 创建文件                       |
| git	add 文件名        | 添加文件/更新提交的内容        |
| git commit -m "提交说明" | 执行提交文件,进行说明          |
| git status               | 查看Git 所处状态               |
| git diff 文件名          | 查看修改	在未添加状态下进行 |
| git diff HEAD^ HEAD      | 和上一次修改内容进行比较       |
| git checkout 文件名      | 丢弃工作区的改动               |
| git mv 文件名 新文件名   | 更改文件名                     |
| history                  | 查看历史命令                   |
|git reset HEAD 文件名 | 从暂存区返回工作区|
|git rm 文件名 | 将文件从版本库中删除并git commit |
|git checkout| 其实是用版本库里的版本替换工作区的版本|





## 多人协作

当从远程库克隆的时候实际上就已经把本地的 master 和远程的master分支对应起来了 , 并且仓库的默认名是origin     要查看远程仓库的信息, 用`git remote`

