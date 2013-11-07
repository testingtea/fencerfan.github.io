---
author: zhengzhiteng
comments: true
date: 2013-03-01 08:28:51+00:00
layout: post
slug: plsql%e8%bf%9c%e7%a8%8b%e8%bf%9e%e6%8e%a5oracle%e6%9c%8d%e5%8a%a1%e5%99%a8%e8%ae%be%e7%bd%ae
title: PL/SQL远程连接oracle服务器设置
wordpress_id: 149
categories:
- 数据库
---

这里介绍的是安装客户端，再安装PL/SQL developer后进行远程连接oracle服务器的步骤。

本步骤中的PL/SQL安装在windows7下，oracle服务器为oracle11gR2。



首先，从官网下载instant client，本次试验是选择Instant Client for Microsoft Windows(32-bit)中的instantclient-basic-nt-11.2.0.3.0.zip，当前官网地址为：

http://www.oracle.com/technetwork/database/features/instant-client/index-097480.html ，将该文件解压出来，如解压后所在目录为C:\oracleclient\instantclient_11_2 ，在该目录下建立子目录NETWORK\ADMIN ，而后再创建tnsnames.ora 文件。文件内容大致如下：

oracle服务实例 =

(DESCRIPTION =

(ADDRESS = (PROTOCOL = TCP)(HOST = oracle服务器IP地址)(PORT = 1521))

(CONNECT_DATA =

(SERVER = DEDICATED)

(SERVICE_NAME = oracle服务实例)

)

)

为保持一致，从oracle服务器上获取该文件后再进行相应的修改，该文件路径在：oracle安装目录\11.2.0\dbhome_1\NETWORK\ADMIN\tnsnames.ora 。

接下来便是安装PL/SQL developer，注意安装路径不使用默认的C:\Program Files (软件的某个bug导致)。安装好后运行程序，首先弹出登录界面，先不进行登录，选择取消后进入主界面，选择菜单tools->preferences->connection,设置如下两项：

Oracle Home: D:\Program Files\instantclient_11_2      #instant client解压目录

OCI library: D:\Program Files\instantclient_11_1\oci.dll       #oci库文件路径，oci.dll应该在instant client目录下

重启程序，在弹出的登录界面中Database下拉选项里有刚刚配置的远程服务器上的服务实例了。



附录：

登录问题：

ORA-12170：TNS：connection timeout occurred

检查网络连接是否通畅，注意oracle服务器防火墙是否开启。



ORA-12170：TNS：no listener

检查oracle服务器各项服务是否已经开启。



PL/SQL Developer 9.x注册码

Product Code：46jw8l8ymfmp2twwbuur8j9gv978m2q2du
serial Number：307254
password：xs374ca
