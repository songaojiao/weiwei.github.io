---
layout: post
title: 个人博客搭建 
summary: Markdown is a way to style text on the web.
featured-img:  emile-perron-190221
---

# 							个人博客搭建 

参考资料	:	<https://jekyllrb.com/>

1. 安装完整的[Ruby开发环境](https://jekyllrb.com/docs/installation/)

   Jekyll是可以在大多数系统上安装的[Ruby Gem](https://jekyllrb.com/docs/ruby-101/#gems)。 可以通过 `gcc -v` 来查看是否安装

   

   在安装Jekyll之前，我们需要确保拥有所有必需的依赖项。

   ` sudo apt-get install ruby-full build-essential zlib1g-dev `

   最好避免以root用户身份安装Ruby Gems。因此，我们需要为您的用户帐户设置一个gem安装目录。以下命令将环境变量添加到您的`~/.bashrc`文件中，以配置gem安装路径。现在运行它们 : 

   ```php
   echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
   echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
   echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
   source ~/.bashrc
   ```

   最后，安装Jekyll： `gem install jekyll bundler` 

   

2. 安装Jekyll和[bundler ](https://jekyllrb.com/docs/ruby-101/#bundler)[gem](https://jekyllrb.com/docs/ruby-101/#gems) 

   ` gem install jekyll bundler `

   

3. 在以下位置创建一个新的Jekyll网站 `./mylog` 

   `jekyll new myblog` 

4. 切换到新目录

   `cd myblog` 

5. 建立站点并使其在本地服务器上可用

   ` bundle exec jekyll serve ` 

6. 现在浏览到[http：// localhost：4000](http://localhost:4000/)



中间可能会遇到任何意外错误, 其中我遇到的是宝石捆绑器什么的, 出现过两次  

使用 ` gem install bundler ` 安装[Bundler](https://rubygems.org/gems/bundler)。



打开[http：// localhost：4000](http://localhost:4000/) 网页就可以看到个人博客了, 当然还没完全做好, 只是一个简单的页面

然后打开Gitbub  创建一个新的远程库	 命名为用户名+.github.io例如`ljshllw.github.io` 



创建SSH秘钥

`git config --global user.name "yourname"` 

`git config --global user.email "youremail"`

`ssh-keygen -t rsa -C "youremail"` 

登陆`github`找到`setting`添加`SSH key` 将刚才生成的`id_rsa.pub`（文件所在地址生成在`ssh-keygen`命令的时候有显示查看`gitbash`记录即可得知）文件里的内容粘上去



登陆`github`选择`gitpage`仓库，选择`settings`，下滑找到`Github Pages` 在`Custom domain`里填入你的域名，然后点击`Save`，稍等一会就好了，之后会默认转成`HTTPS`。SSL证书来自`Let's Encrypt`。



![](https://img2018.cnblogs.com/blog/1425720/201905/1425720-20190509225543111-1134636955.png)

将自己的域名填写到里面 Custom domain 里面  添加  上传一个CNAME文件, 里面写需要配置的域名  



然后上传模板, 也可以使用系统模板 系统的主题没怎么研究   自己上传模板就是将html页面上传到远程库里 里面要有index.html文件   不然不会自动进入主页面  

可以测试一下试试 