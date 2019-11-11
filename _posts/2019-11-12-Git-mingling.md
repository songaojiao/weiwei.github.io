---
layout: post
title: git 常用操作命令
summary: Markdown is a way to style text on the web.
featured-img:  emile-perron-190221
---

# git 常用操作命令

初始化: 创建一个git仓库 , 创建之后就会在当前目录生成一个.git的文件

`git init`

添加文件: 把文件添加到缓冲区

` git add filename` 

添加所有文件到缓冲区 (从目前掌握的水平看，和后面加“.”的区别在于，加all可以添加被手动删除的文件，而加“.”不行）：

`git add .`

`git add --all`

删除文件: 

`git rm filename`

提交：提交缓冲区的所有修改到仓库(注意：如果修改了文件但是没有add到缓冲区，也是不会被提交的)

` git commit -m '提交说明'`

commit可以一次性提交所有缓冲区的文件

查看git 库状态, 未提交的文件, 分为两种, add过已经在缓存区的, 没有add 过的

`git status`

如果文件修改了, 还没有提交 可以比较文件修改前后的差异

`git diff filename`

查看日志 

`git log`     `git reflog` 

常用git 命令

```
git clone 地址 // 克隆远程仓库
git clone -b 分支名 地址 // 克隆分支的代码到本地
```

查看git常用命令

`git helper -a `// 查看全部git子命令

查看文件的修改历史

`git blame 文件名` // 查看该文件的修改历史

`git blame -L 100,10 文件名 `// 从100行开始，到110行 逐行查看文件的修改历史

`git clean -n` // 列出打算清除的档案(首先会对工作区的内容进行提示) -f (真正的删除)

删除放入暂存区文件的方法（已commit后）

`git rm 文件名 `// 将该文件从commit后撤回到add后

修改文件名以及移动

`git mv a b `// 把a文件名字改成b 并且直接放入git add后的暂存区

`git mv b ./demos/ `// 把b文件移动到demos文件夹下

版本回退 : 可以将仓库当前裆裤会退到历史的某个版本

`git reset`  

第一种方法: 回退到上一个版本 (HEAD代表当前版本 一个^代表上一个版本或~num )

`git reset --hard HEAD^`   `git reset --hard HEAD~1`

第二种方法:退到指定版本 d7b5 是版本号

`git reset --hard d7b5 ` 
`git stash` // 把暂存区的内容 暂时放在其他中 使暂存区变空

`git stash list` // 查看stash了哪些存储

`git stash pop `// 将stash中的内容恢复到当前目录，将缓存堆栈中的对应stash删除

git 分支管理

查看分支的情况, 前面带*号的就是当前分支

`git branch `

创建分支

`git branch 分支名`

创建分支 并切换到分支

`git checkout  -b 分支名`

切换分支

`git checkout 分支名`

合并某分支的内容到当前分支

`git merge 分支名`

删除分支

`git branch -d 分支名`

`git branch -m 旧分支名 新分支名 `// 修改分支名

`git branch -r `// 列出远程分支(远程所有分支名) 参数-a查看本地及远程分支

我们一定要学会`git branch -vv -a`这个命令，这个是查询本地仓库+远程仓库+跟踪关系最全的命令了



新建标签, 默认为最新版本, 后面加上版本号参数则可指定版本增加标签

`git tag 标签名 版本号`

查看所有标签 : 

 `git tag`

查看标签的详细信息

`git show 标签名`

将tag提交到远程仓库

`git push origin --tags`       `git push origin v1.0`



git 远程库相关

`git remote add origin git://127.0.0.1/abc.git` 这样就可以添加远程库的abc

`git remote remove origin`  移除远程仓库

将本地仓库内容推送到远程仓库 (-u 表示第一次推送master 分支的所有内容, 后面推送就不需要-u), 跟commit 的区别在于一个是提交到本地仓库, 一个是提交到远程仓库

`git push -u origin master ` 

从远程库更新内容到本地 (相当于svn的update)

`git pull`

tips : 如果push的时候, 本地和文件和远端文件有冲突, 就要先pull 、然后手动解决冲突, 才能继续push

强制推送 (慎用, 除非你认为其他冲突等可以丢弃 或者不是很重要)

`git push -- force` 

创建文件等小命令


```

echo 1234 >> a // 把1234这个内容放入a文件

cat a // 打开a文件 读取出a文件中的内容

mkdir test // 创建test文件夹

rm 文件名 // 删除文件

pwd // 打印当前工作路径

```

### 开始一个工作区 (参见	: git help tutorial)

命令|作用
--|--
clone|克隆一个仓库到一个新目录
init|创建一个控Git	仓库或从新初始化一个已存在的仓库

### 在当前变更上工作	(参见	: git help everyday)
命令|作用
--|--
add|添加文件内容至索引
mv|移动或重命名一个文件、目录或符号链接
reset|重置当前HEAD	到指定状态
rm|从工作区和索引中删除文件

### 查看历史和状态	(参见	: git help)
命令|作用
--|--
bisect|通过二分查找定位引入	bug	的提交

Linux 常用命令大全   方便查看   <https://blog.csdn.net/luansj/article/details/97272672>

