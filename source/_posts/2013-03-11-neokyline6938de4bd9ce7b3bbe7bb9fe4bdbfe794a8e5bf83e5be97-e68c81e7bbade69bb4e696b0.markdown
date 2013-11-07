---
author: wangsx
comments: true
date: 2013-03-11 05:55:27+00:00
layout: post
published: false
slug: neokylin%e6%93%8d%e4%bd%9c%e7%b3%bb%e7%bb%9f%e4%bd%bf%e7%94%a8%e5%bf%83%e5%be%97-%e6%8c%81%e7%bb%ad%e6%9b%b4%e6%96%b0
title: neokylin操作系统使用心得(更新中）
wordpress_id: 183
categories:
- 学习报告
---


	
  1. 在neokylin操作系统上安装mysql。
a、在VirtualBox用neokylin的iso镜像安装操作系统，如 neokylin-3.2.2-x86.iso。
b、装完系统后，开启虚拟机。 在Settings-Storage 处再将neokylin-3.2.2-x86.iso添加进来
c、执行如下语句，将光盘挂载到虚拟机的/media目录下，以便能查看光盘里的文件 。mount /dev/dvd /media
d、cd /media/KYLIN这个目录 ，里面都很多rpm包，基本上能满足用户的各种需求。mysql安装包就在其中。
e、用ls mysql*找到 mysql-server-5.1.47-4.1.ky3.i686.rpm。执行 rpm -ivh mysql-server-5.1.47-4.1.ky3.i686.rpm发现出现依赖问题perl-DBD-MySQL is needed by mysql-server-5.1.47-4.1.ky3.i686。
f、此时仍然在此安装目录下查找 perl-DBD-MySQL，发现有perl-DBD-MySQL-4.013-3.1.ky3.i686.rpm。执行 rpm -ivh perl-DBD-MySQL-4.013-3.1.ky3.i686.rpm安装perl-DBD-MySQL。
g、再执行  rpm -ivh mysql-server-5.1.47-4.1.ky3.i686.rpm发现mysql安装成功。
h、推出光盘目录。执行/etc/init.d/mysqld start启动mysql，密码默认为空，发现能成功进入mysql了。
从此问题可以看出，光盘上已经有了我们所需要的包，不需再到网上下载了！只需挂载光盘，读取盘中的文件即可安装了！！


