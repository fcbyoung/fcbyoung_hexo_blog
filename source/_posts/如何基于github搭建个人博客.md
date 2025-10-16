---
title: 如何基于github搭建个人博客
date: 2025-09-22 15:57:29
tags: [github,hexo]


---

每个码农都有一个搭建个人博客的梦想。
虽然现在写代码的机会比较少了，不过这个梦想依然在心中等待实现。拖了很久，最近因为工作和学习上的事情，打算搭建一个新的平台来记录一些内容当做笔记，简直没有比个人博客更适合的平台了。这下不能再拖了。

说干就干。通过网上查阅到的教程，一步一步实现个人博客搭建的功能。这里顺便把搭建的过程记录下来，正好当做新博客的第一篇内容，再适合不过了。



1.我们需要用到github，具体需要登录github页面以及在本地搭建git环境，并为git配置SSH key信息。这部分之前都已经完成了，步骤略。



2.我们需要在给电脑安装node.js

访问网址https://nodejs.org/en/download/

点击Windows Installer(.msi)链接进行下载安装。

安装过程没有什么特殊操作，一路next即可。

安装好之后，可以在git bash终端输入命令node -v进行验证。



3.在本地安装Hexo

在git bash终端输入命令npm install hexo -g进行安装

显示安装完成后，可输入命令hexo -v进行验证



4.安装hexo依赖

在git bash终端输入命令npm install --save hexo-deployer-git



5.到这里基本的安装流程就已经结束了，下面开始博客目录的搭建

首先需要新建一个专门的本地保存博客的目录。比如就叫E:\young\fcbyoung\

在git bash终端进入这个目录，然后输入hexo init命令完成初始化。如图

*![]( /images/微信图片_20250922135054_41_10.png)*

同时我们可以看到就在我们创建的博客目录文件夹下也出现了一些新建内容

*![]( /images/微信图片_20250922135109_42_10.png)*

接下来使用hexo g命令，生成静态网页。完成后使用hexo s命令进行预览

*![]( /images/微信图片_20250922135232_44_10.png)*

两步都完成后，可以看到生成了一个http://localhost:4000/的链接

在浏览器访问此链接，可以打开一个本地页面

*![]( /images/微信图片_2025-09-22_165757_443.png)*

页面已生成，创建页面的第一步已经完成。

接下来我们需要借助github将网页运行上线。

6.在github页面，选择New repository，新建一个github仓库

注意：给仓库起名一定要遵循固定的格式，用户名.github.io

比如我的github用户名叫fcbyoung，那么我的新仓库名称就必须是fcbyoung.github.io

同时建议点击选中Add a README

其余没有什么需要特别注意的事项，设置好之后点击create即可。

接下来回到本地博客目录，找到_config.yml文件进行编辑，内容如下：

```
deploy:
  type: git
  repo: git@github.com:fcbyoung/fcbyoung.github.io.git
  branch: main
```

repo后面将自己的仓库地址附上

branch看自己的github仓库在哪个分支下。我的显示在main分支，所以这里就填main

设置好后，在git bash输入命令hexo d，将博客发布到github

*![]( /images/微信图片_20250922150941_75_10.png)*

顺利发布后，在浏览器地址栏输入自己的链接，即可成功访问

*![]( /images/0000.PNG)*



