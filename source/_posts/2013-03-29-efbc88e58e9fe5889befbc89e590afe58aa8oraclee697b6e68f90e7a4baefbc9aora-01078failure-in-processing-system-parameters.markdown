---
author: liangzhongxing
comments: true
date: 2013-03-29 08:07:12+00:00
layout: post
slug: '%ef%bc%88%e5%8e%9f%e5%88%9b%ef%bc%89%e5%90%af%e5%8a%a8oracle%e6%97%b6%e6%8f%90%e7%a4%ba%ef%bc%9aora-01078failure-in-processing-system-parameters'
title: （原创）启动Oracle时提示：ORA-01078:failure in processing system parameters
wordpress_id: 216
categories:
- 数据库
tags:
- OEL initorcl.ora spfile
---

一、使用环境
操作系统：OEL 6.3 x64
数据库：Oracle 11.2.0.1.0
数据库主目录：/u01/app/oracle/product/10.2.0/

二、问题描述
用sys用户登录sqlplus后，用startup命令启动Oracle时提示：
ORA-01078:failure in processing system parameters
LRM-00109: could not open parameter file '/u01/app/oracle/product/11.2.0/db_1/dbs/initorcl.ora'

三、错误原因
在oracle9i、10g、11g最近几个版本中，数据库默认使用spfile启动数据库，如果spfile不存在，则就会出现上述错误。

四、解决方法
方法一：

用find /u01 -name pfile命令查找pfile文件的位置，/u01/app/oracle/admin/orcl/pfile/
将$ORACLE_BASE/admin/orcl/pfile目录下的init.ora.2212013132036形式的文件copy 到$ORACLE_HOME/dbs目录下命名为initorcl.ora即可。

（注：initorcl.ora中的orcl为你的实例名 ORACLE_SID，这里我的SID为：center）

方法二：
将$ORACLE_HOME/dbs目录下spflieorcl.ora改名为spfilecenter.ora即可。（注：spfilecenter.ora中的center为环境变量中设置的SID，我的是center）
