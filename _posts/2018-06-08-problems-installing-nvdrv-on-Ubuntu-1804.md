---
layout: post
title: Ubuntu18.04 LTS下NVIDIA显卡遇到的几个坑
key: 10003
tags: Ubuntu
category: blog
date: 2018-06-08 
---
没安装独立显卡驱动的时候频繁死机，解决方法如下：
先禁用nouveau：
打开/etc/modprobe.d/blacklist.conf在最后加上
`blacklist nouveau`，然后执行`sudo update-initramfs` 重启
然后使用PPA安装驱动：

    sudo add-apt-repository ppa:graphics-drivers/ppa

    sudo apt-get update
用ubuntu-drivers device找到合适的驱动版本，用命令`sudo apt-get install`安装
重启后用`sudo nvidia-smi`查看是否安装成功

进行显卡切换，使用NVIDIA X Server Settings中的PRIME Profiles切换Intel显卡时发现重启后无法打开x server切换回来，发现只能用命令

    ~$ prime-select intel
    ~$ prime-select nvidia
进行切换