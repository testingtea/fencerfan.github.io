---
author: shengrenwang
comments: true
date: 2013-05-17 08:30:44+00:00
layout: post
slug: ubuntu-server%e4%b8%8b%e5%a6%82%e4%bd%95%e5%ae%89%e8%a3%85%e5%9b%be%e5%bd%a2%e7%95%8c%e9%9d%a2
title: ubuntu server下如何安装图形界面
wordpress_id: 273
categories:
- 虚拟机
---

一,连接网络，确保网络通畅.

二,进入图形界面的命令是startX，敲击后会有安装xinit的提示,输入如下命令:

sudo apt-get install xinit

安装完，终端由黑色界面变成白底黑字。出现X型的鼠标指针。

三,安装环境管理器

sudo apt-get install gdm

四,安装桌面环境

sudo apt-get install Kbuntu-desktop

如果只想装界面的核心环境，或者网速比较曼的话，可以

sudo apt-get install gnome-core或者kde-corexface4

五,如果你装的是CORE的，那么你还需要做以下的工作:

1.安装新立得软件包管理器:

sudo apt-get install gsynaptic

2.安装中文支持（能够显示中文):

sudo apt-get install language-support-zh

3.从新立得软件包管理器中选择中文输入法支持和中文界面支持

4.使用新立得软件包管理器安装其他你想要的软件

六,重新启动，即可见图形登陆界面。


