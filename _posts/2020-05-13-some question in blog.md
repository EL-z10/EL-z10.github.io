---
layout: post
title:  "博客一些功能实现"
date:   2020-05-13 
tags:  blog
color: rgb(238 130 238)
cover: '../assets/post/jekyll.jpg'
subtitle: '插图，下载链接'
---



## md插入图片问题

先码个md[加图语法](https://www.jianshu.com/p/280c6a6f2594)

一开始想用相对路径，方法如下

[https://blog.csdn.net/tian_ci/article/details/82909919](https://blog.csdn.net/tian_ci/article/details/82909919)

[![YrNKMt.png](https://s1.ax1x.com/2020/05/15/YrNKMt.png)](https://imgchr.com/i/YrNKMt)

此时md文件中可以正常显示图片，但是push到网上还是显示不出来。

经查，jekyll不会复制_post文件里的资产，得放在根目录下一个`不是以下划线开头`的文件夹里头。

![YrNLQI.png](https://s1.ax1x.com/2020/05/15/YrNLQI.png)

遂把图片丢到/assets/images里面，md文件显示失败

考虑可能是相对路径没用对？

搜一下相对路径用法：

`./assets/`这样写表示，当前目录中的assets文件夹
`../assets/`这样写表示，当前目录的上一层目录中的assets文件夹
`/assets/`这样写表示，项目根目录（可以指磁盘根目录，也可以指项目根目录，据实际情况而定）



遂把图片丢到../assets/images里面，md文件显示失败（？）

再来把图片丢到../assets里面，md文件显示成功

![Yr0faV.png](https://s1.ax1x.com/2020/05/15/Yr0faV.png)

然而push上去还是显示不了。。。~~心态崩了~~

![test1](../assets/test1.png)

换方法用图床。七猫云好麻烦QAQ，于是用的[路过图床](https://imgchr.com/)，免费方便，图传上去复制图片链接即可。

```
![图片名字]（图片链接）
![Yr0faV.png](https://s1.ax1x.com/2020/05/15/Yr0faV.png)
```

