---
layout: post
title: Windows 10的Ubuntu子系统运行图形化程序的简单方法
key: 10002
tags: Ubuntu
category: blog
date: 2018-05-18 
---
想在Ubuntu上用opencv和摄像头做个小东西，但没图形化界面肯定是非常不便的，见到很多用ssh的方法登陆图形化界面，感觉不太好用，于是就用Xming实现了图形化应用程序的运行。各个应用程序用单独的窗口

![](https://i.imgur.com/9IvMGWk.png)

##步骤
下载安装Xming（[下载地址](https://sourceforge.net/projects/xming/)），一路点击下一步，安装完成后点击Xlaunch.
![](https://i.imgur.com/zwMakIS.png)

在“Select display settings”选项可以按照喜好选择，我用的是“Multiple windows”
完成后，回到Linux子系统，要启动图形化窗口的应用程序（如Firefox）输入命令：
    DISPLAY=:0 firefox
即可