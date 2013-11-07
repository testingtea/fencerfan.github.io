---
author: shengrenwang
comments: true
date: 2013-03-17 15:28:43+00:00
layout: post
slug: linux%e4%b8%8b%e5%88%9b%e5%bb%baoracle%e6%95%b0%e6%8d%ae%e5%ba%93orcl1%e5%ae%9e%e4%be%8b
title: linux下创建oracle数据库orcl1实例
wordpress_id: 203
categories:
- 学习报告
---

**1，设置环境变量**

装oracle的时候，设置了一些环境变量，下面这些环境变量是跟这次安装有关的

ORACLE_HOME=/home/oracle/app/ora10
ORACLE_OWNER=oracle
DB_HOME=/home/oracle/app/ora10/oradata
ORACLE_SID=orcl //这个是安装orcl数据库的sid。

**2，创建pfile文件**

oracle安装完成后，系统有一个数据库orcl，我们可以利用它来创建pfile文件

cd $ORACLE_HOME/dbs
strings spfileorcl.ora >initorcl1.ora

然后在手动将initorcl1.ora里面orcl,全部改成orcl1，这样pfile文件就做好了。

**3，生成密码文件**

sudo cp $ORACLE_HOME/bin/orapwd /usr/local/bin/
orapwd file=orapworcl password=dingjia //目录是$ORACLE_HOME/dbs,前面已经有了

**4，创建oracle数据库目录**

mkdir $ORACLE_HOME/admin/orcl1
cd $ORACLE_HOME/admin/orcl1
mkdir adump bdump cdump dpdump pfile udump
mkdir $DB_HOME/orcl1

**5，修改tnsnames.ora和listener.ora**

//这个在tnsnames.ora中加上
ORCL1 =
(DESCRIPTION =
(ADDRESS = (PROTOCOL = TCP)(HOST = Kylin-10g)(PORT = 1521))
(CONNECT_DATA =
(SERVER = DEDICATED)
(SERVICE_NAME = orcl1)
)
)

//这个在listener.ora中加上
(SID_DESC =
(SID_NAME = orcl1)
(GLOBAL_DBNAME=orcl1)
(ORACLE_HOME = /home/oracle/app/ora10)
(PROGRAM = extproc)
)

其实就是将各自文件中orcl的部分，拷贝一下，把orcl改成orcl1。修改这个为了sqlplus连接实例用的。

**6，修改实例入口**

export ORACLE_SID=orcl1

前面提到了环境变量ORACLE_SID=orcl，在这里要换掉，不然用sqlplus会进入到orcl数据库的。

**7，创建数据库**

//1,sqlplus登录
sqlplus / as sysdba

//2,启动不加载实例
SQL> startup nomount

//3,从create开始到最后的冒号，直接copy进去执行就行了。
SQL> create database orcl1
LOGFILE
GROUP 1 ('$DB_HOME/orcl1/redo01.log','$DB_HOME/orcl1/redo01_1.log') size 100m reuse,
GROUP 2 ('$DB_HOME/orcl1/redo02.log','$DB_HOME/orcl1/redo02_1.log') size 100m reuse,
GROUP 3 ('$DB_HOME/orcl1/redo03.log','$DB_HOME/orcl1/redo03_1.log') size 100m reuse
MAXLOGFILES 50
MAXLOGMEMBERS 5
MAXLOGHISTORY 200
MAXDATAFILES 500
MAXINSTANCES 5
ARCHIVELOG
CHARACTER SET UTF8
NATIONAL CHARACTER SET UTF8
DATAFILE '$DB_HOME/orcl1/system01.dbf' SIZE 1000M EXTENT MANAGEMENT LOCAL
SYSAUX DATAFILE '$DB_HOME/orcl1/sysaux01.dbf' SIZE 1000M
UNDO TABLESPACE UNDOTBS1 DATAFILE '$DB_HOME/orcl1/undo.dbf' SIZE 500M
DEFAULT TEMPORARY TABLESPACE TEMP TEMPFILE '$DB_HOME/orcl1/temp.dbf' SIZE 500M;

**8，创建ORACLE的数据字典**

SQL> @$ORACLE_HOME/rdbms/admin/catalog.sql;
SQL> @$ORACLE_HOME/rdbms/admin/catproc.sql;

**9，简单设置一下权限**

SQL> alter user system identified by orcl1;
SQL> grant sysdba to system;
SQL> shutdown immediate;
SQL> startup;

**10，查看一下表空间，以及管理方式**



SQL> select tablespace_name,extent_management from dba_tablespaces;

TABLESPACE_NAME EXTENT_MAN
------------------------------ ----------
SYSTEM LOCAL
UNDOTBS1 LOCAL
SYSAUX LOCAL
TEMP LOCAL


