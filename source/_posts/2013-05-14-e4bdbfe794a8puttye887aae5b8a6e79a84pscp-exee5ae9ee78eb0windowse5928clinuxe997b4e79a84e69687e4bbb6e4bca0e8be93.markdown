---
author: zhengzhiteng
comments: true
date: 2013-05-14 07:29:42+00:00
layout: post
slug: '%e4%bd%bf%e7%94%a8putty%e8%87%aa%e5%b8%a6%e7%9a%84pscp-exe%e5%ae%9e%e7%8e%b0windows%e5%92%8clinux%e9%97%b4%e7%9a%84%e6%96%87%e4%bb%b6%e4%bc%a0%e8%be%93'
title: 使用putty自带的pscp.exe实现windows和linux间的文件传输
wordpress_id: 248
categories:
- 测试方法
---

在我们的日常性能测试中，难免会遇到需要进行基准测试。

这时候，通常我们会采用搭建ftp进行文件上传和下载来获取当前两台计算机之间的网络传输基准数据。

接下来要介绍的是使用putty自带的pscp.exe来实现windows和linux间的文件传输，该方法可在无法搭建ftp时，快速简便进行基准测试，由于是经过加密后传输的，所以不能作为正常传输速度基准测试的数据，只能作为加密传输速度基准测试的数据。用法基本与scp命令相同。

首先下载putty，官方下载地址为：

http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html

1.下载putty.zip并解压

2.cmd命令行进入putty目录

3.将文件上传至linux系统，pscp 本地文件 用户名@IP：上传目录

如：pscp c:\agent.log  root@192.168.88.172:/root

4.将文件下载至windows系统，pscp 用户名@IP：下载文件路径  存放文件路径

如：pscp root@192.168.88.172:/root/agent.log  c:\download
